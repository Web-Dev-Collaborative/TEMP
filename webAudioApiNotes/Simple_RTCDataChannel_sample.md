-   <a href="#content" id="skip-main">Skip to main content</a>
-   <a href="#main-q" id="skip-search">Skip to search</a>
-   <a href="#select-language" id="skip-select-language">Skip to select language</a>

-   Technologies
    -   [Technologies Overview](https://developer.mozilla.org/en-US/docs/Web)
    -   [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML)
    -   [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
    -   [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
    -   [Graphics](https://developer.mozilla.org/en-US/docs/Web/Guide/Graphics)
    -   [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP)
    -   [APIs](https://developer.mozilla.org/en-US/docs/Web/API)
    -   [Browser Extensions](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions)
    -   [MathML](https://developer.mozilla.org/en-US/docs/Web/MathML)
-   References & Guides
    -   [Learn web development](https://developer.mozilla.org/en-US/docs/Learn)
    -   [Tutorials](https://developer.mozilla.org/en-US/docs/Web/Tutorials)
    -   [References](https://developer.mozilla.org/en-US/docs/Web/Reference)
    -   [Developer Guides](https://developer.mozilla.org/en-US/docs/Web/Guide)
    -   [Accessibility](https://developer.mozilla.org/en-US/docs/Web/Accessibility)
    -   [Game development](https://developer.mozilla.org/en-US/docs/Games)
    -   [...more docs](https://developer.mozilla.org/en-US/docs/Web)
-   Feedback
    -   [Send Feedback](https://developer.mozilla.org/en-US/docs/MDN/Contribute/Feedback)
    -   [Contribute to MDN](https://developer.mozilla.org/en-US/docs/MDN/Contribute)
    -   [Report a content issue 🌐](https://github.com/mdn/content/issues/new)
    -   [Report a platform issue 🌐](https://github.com/mdn/yari/issues/new)

Search MDN

1.  <a href="https://developer.mozilla.org/en-US/docs/Web" class="breadcrumb"><span data-property="name">Web technology for developers</span></a>
2.  <a href="https://developer.mozilla.org/en-US/docs/Web/API" class="breadcrumb"><span data-property="name">Web APIs</span></a>
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API" class="breadcrumb-penultimate"><span data-property="name">WebRTC API</span></a>
4.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Simple_RTCDataChannel_sample" class="breadcrumb-current-page"><span data-property="name">A simple RTCDataChannel sample</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [The HTML](#the_html)
-   [The JavaScript code](#the_javascript_code)
-   [Next steps](#next_steps)
-   [See also](#see_also)

A simple RTCDataChannel sample
==============================

The [`RTCDataChannel`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel) interface is a feature of the [WebRTC API](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API) which lets you open a channel between two peers over which you may send and receive arbitrary data. The API is intentionally similar to the [WebSocket API](https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API), so that the same programming model can be used for each.

In this example, we will open an [`RTCDataChannel`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel) connection linking two elements on the same page. While that's obviously a contrived scenario, it's useful for demonstrating the flow of connecting two peers. We'll cover the mechanics of accomplishing the connection and transmitting and receiving data, but we will save the bits about locating and linking to a remote computer for another example.

[The HTML](#the_html "Permalink to The HTML")
---------------------------------------------

First, let's take a quick look at the <a href="https://github.com/mdn/samples-server/tree/master/s/webrtc-simple-datachannel/index.html" class="external">HTML that's needed</a>. There's nothing incredibly complicated here. First, we have a couple of buttons for establishing and closing the connection:

    <button id="connectButton" name="connectButton" class="buttonleft">
      Connect
    </button>
    <button id="disconnectButton" name="disconnectButton" class="buttonright" disabled>
      Disconnect
    </button>

Then there's a box which contains the text input box into which the user can type a message to transmit, with a button to send the entered text. This [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) will be the first peer in the channel.

      <div class="messagebox">
        <label for="message">Enter a message:
          <input type="text" name="message" id="message" placeholder="Message text"
                  inputmode="latin" size=60 maxlength=120 disabled>
        </label>
        <button id="sendButton" name="sendButton" class="buttonright" disabled>
          Send
        </button>
      </div>

Finally, there's the little box into which we'll insert the messages. This [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) block will be the second peer.

    <div class="messagebox" id="receivebox">
      <p>Messages received:</p>
    </div>

[The JavaScript code](#the_javascript_code "Permalink to The JavaScript code")
------------------------------------------------------------------------------

While you can just <a href="https://github.com/mdn/samples-server/tree/master/s/webrtc-simple-datachannel/main.js" class="external">look at the code itself on GitHub</a>, below we'll review the parts of the code that do the heavy lifting.

The WebRTC API makes heavy use of [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)s. They make it very easy to chain the steps of the connection process together; if you haven't already read up on this functionality of [ECMAScript 2015](https://developer.mozilla.org/en-US/docs/Archive/Web/JavaScript/New_in_JavaScript/ECMAScript_2015_support_in_Mozilla), you should read up on them. Similarly, this example uses [arrow functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions) to simplify syntax.

### [Starting up](#starting_up "Permalink to Starting up")

When the script is run, we set up a `load` event listener, so that once the page is fully loaded, our `startup()` function is called.

    function startup() {
      connectButton = document.getElementById('connectButton');
      disconnectButton = document.getElementById('disconnectButton');
      sendButton = document.getElementById('sendButton');
      messageInputBox = document.getElementById('message');
      receiveBox = document.getElementById('receivebox');

      // Set event listeners for user interface widgets

      connectButton.addEventListener('click', connectPeers, false);
      disconnectButton.addEventListener('click', disconnectPeers, false);
      sendButton.addEventListener('click', sendMessage, false);
    }

This is quite straightforward. We grab references to all the page elements we'll need to access, then set [`event listeners`](https://developer.mozilla.org/en-US/docs/Web/API/EventListener "event listeners") on the three buttons.

### [Establishing a connection](#establishing_a_connection "Permalink to Establishing a connection")

When the user clicks the "Connect" button, the `connectPeers()` method is called. We're going to break this up and look at it a bit at a time, for clarity.

**Note:** Even though both ends of our connection will be on the same page, we're going to refer to the one that starts the connection as the "local" one, and to the other as the "remote" end.

#### Set up the local peer

    localConnection = new RTCPeerConnection();

    sendChannel = localConnection.createDataChannel("sendChannel");
    sendChannel.onopen = handleSendChannelStatusChange;
    sendChannel.onclose = handleSendChannelStatusChange;

The first step is to create the "local" end of the connection. This is the peer that will send out the connection request.  The next step is to create the [`RTCDataChannel`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel) by calling [`RTCPeerConnection.createDataChannel()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/createDataChannel) and set up event listeners to monitor the channel so that we know when it's opened and closed (that is, when the channel is connected or disconnected within that peer connection).

It's important to keep in mind that each end of the channel has its own [`RTCDataChannel`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel) object.

#### Set up the remote peer

    remoteConnection = new RTCPeerConnection();
    remoteConnection.ondatachannel = receiveChannelCallback;

The remote end is set up similarly, except that we don't need to explicitly create an [`RTCDataChannel`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel) ourselves, since we're going to be connected through the channel established above. Instead, we set up a `datachannel` event handler; this will be called when the data channel is opened; this handler will receive an `RTCDataChannel` object; you'll see this below.

#### Set up the ICE candidates

The next step is to set up each connection with ICE candidate listeners; these will be called when there's a new ICE candidate to tell the other side about.

**Note:** In a real-world scenario in which the two peers aren't running in the same context, the process is a bit more involved; each side provides, one at a time, a suggested way to connect (for example, UDP, UDP with a relay, TCP, etc.) by calling [`RTCPeerConnection.addIceCandidate()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/addIceCandidate), and they go back and forth until agreement is reached. But here, we just accept the first offer on each side, since there's no actual networking involved.

        localConnection.onicecandidate = e => !e.candidate
            || remoteConnection.addIceCandidate(e.candidate)
            .catch(handleAddCandidateError);

        remoteConnection.onicecandidate = e => !e.candidate
            || localConnection.addIceCandidate(e.candidate)
            .catch(handleAddCandidateError);

We configure each [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection) to have an event handler for the `icecandidate` event.

#### Start the connection attempt

The last thing we need to do in order to begin connecting our peers is to create a connection offer.

        localConnection.createOffer()
        .then(offer => localConnection.setLocalDescription(offer))
        .then(() => remoteConnection.setRemoteDescription(localConnection.localDescription))
        .then(() => remoteConnection.createAnswer())
        .then(answer => remoteConnection.setLocalDescription(answer))
        .then(() => localConnection.setRemoteDescription(remoteConnection.localDescription))
        .catch(handleCreateDescriptionError);

Let's go through this line by line and decipher what it means.

1.  First, we call [`RTCPeerConnection.createOffer()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/createOffer) method to create an [SDP](https://developer.mozilla.org/en-US/docs/Glossary/SDP) (Session Description Protocol) blob describing the connection we want to make. This method accepts, optionally, an object with constraints to be met for the connection to meet your needs, such as whether the connection should support audio, video, or both. In our simple example, we don't have any constraints.
2.  If the offer is created successfully, we pass the blob along to the local connection's [`RTCPeerConnection.setLocalDescription()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/setLocalDescription) method. This configures the local end of the connection.
3.  The next step is to connect the local peer to the remote by telling the remote peer about it. This is done by calling `remoteConnection.`[`RTCPeerConnection.setRemoteDescription()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/setRemoteDescription). Now the `remoteConnection` knows about the connection that's being built. In a real application, this would require a signaling server to exchange the description object.
4.  That means it's time for the remote peer to reply. It does so by calling its [`createAnswer()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/createAnswer "createAnswer()") method. This generates a blob of SDP which describes the connection the remote peer is willing and able to establish. This configuration lies somewhere in the union of options that both peers can support.
5.  Once the answer has been created, it's passed into the remoteConnection by calling [`RTCPeerConnection.setLocalDescription()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/setLocalDescription). That establishes the remote's end of the connection (which, to the remote peer, is its local end. This stuff can be confusing, but you get used to it). Again, this would normally be exchanged through a signalling server.
6.  Finally, the local connection's remote description is set to refer to the remote peer by calling localConnection's [`RTCPeerConnection.setRemoteDescription()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/setRemoteDescription).
7.  The `catch()` calls a routine that handles any errors that occur.

**Note:** Once again, this process is not a real-world implementation; in normal usage, there's two chunks of code running on two machines, interacting and negotiating the connection. A side channel, commonly called a “signalling server,” is usually used to exchange the description (which is in **application/sdp** form) between the two peers.

#### Handling successful peer connection

As each side of the peer-to-peer connection is successfully linked up, the corresponding [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection)'s `icecandidate` event is fired. These handlers can do whatever's needed, but in this example, all we need to do is update the user interface:

      function handleLocalAddCandidateSuccess() {
        connectButton.disabled = true;
      }

      function handleRemoteAddCandidateSuccess() {
        disconnectButton.disabled = false;
      }

The only thing we do here is disable the "Connect" button when the local peer is connected and enable the "Disconnect" button when the remote peer connects.

#### Connecting the data channel

Once the [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection) is open, the `datachannel` event is sent to the remote to complete the process of opening the data channel; this invokes our `receiveChannelCallback()` method, which looks like this:

      function receiveChannelCallback(event) {
        receiveChannel = event.channel;
        receiveChannel.onmessage = handleReceiveMessage;
        receiveChannel.onopen = handleReceiveChannelStatusChange;
        receiveChannel.onclose = handleReceiveChannelStatusChange;
      }

The `datachannel` event includes, in its channel property, a reference to a [`RTCDataChannel`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel) representing the remote peer's end of the channel. This is saved, and we set up, on the channel, event listeners for the events we want to handle. Once this is done, our `handleReceiveMessage()` method will be called each time data is received by the remote peer, and the `handleReceiveChannelStatusChange()` method will be called any time the channel's connection state changes, so we can react when the channel is fully opened and when it's closed.

### [Handling channel status changes](#handling_channel_status_changes "Permalink to Handling channel status changes")

Both our local and remote peers use a single method to handle events indicating a change in the status of the channel's connection.

When the local peer experiences an open or close event, the `handleSendChannelStatusChange()` method is called:

      function handleSendChannelStatusChange(event) {
        if (sendChannel) {
          var state = sendChannel.readyState;

          if (state === "open") {
            messageInputBox.disabled = false;
            messageInputBox.focus();
            sendButton.disabled = false;
            disconnectButton.disabled = false;
            connectButton.disabled = true;
          } else {
            messageInputBox.disabled = true;
            sendButton.disabled = true;
            connectButton.disabled = false;
            disconnectButton.disabled = true;
          }
        }
      }

If the channel's state has changed to "open", that indicates that we have finished establishing the link between the two peers. The user interface is updated correspondingly by enabling the text input box for the message to send, focusing the input box so that the user can immediately begin to type, enabling the "Send" and "Disconnect" buttons, now that they're usable, and disabling the "Connect" button, since it is not needed when the conneciton is open.

If the state has changed to "closed", the opposite set of actions occurs: the input box and "Send" button are disabled, the "Connect" button is enabled so that the user can open a new connection if they wish to do so, and the "Disconnect" button is disabled, since it's not useful when no connection exists.

Our example's remote peer, on the other hand, ignores the status change events, except for logging the event to the console:

      function handleReceiveChannelStatusChange(event) {
        if (receiveChannel) {
          console.log("Receive channel's status has changed to " +
                      receiveChannel.readyState);
        }
      }

The `handleReceiveChannelStatusChange()` method receives as an input parameter the event which occurred; this will be an [`RTCDataChannelEvent`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannelEvent).

### [Sending messages](#sending_messages "Permalink to Sending messages")

When the user presses the "Send" button, the sendMessage() method we've established as the handler for the button's `click` event is called. That method is simple enough:

      function sendMessage() {
        var message = messageInputBox.value;
        sendChannel.send(message);

        messageInputBox.value = "";
        messageInputBox.focus();
      }

First, the text of the message is fetched from the input box's [`value`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-value) attribute. This is then sent to the remote peer by calling [`sendChannel.send()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/send "sendChannel.send()"). That's all there is to it! The rest of this method is just some user experience sugar -- the input box is emptied and re-focused so the user can immediately begin typing another message.

### [Receiving messages](#receiving_messages "Permalink to Receiving messages")

When a "message" event occurs on the remote channel, our `handleReceiveMessage()` method is called as the event handler.

      function handleReceiveMessage(event) {
        var el = document.createElement("p");
        var txtNode = document.createTextNode(event.data);

        el.appendChild(txtNode);
        receiveBox.appendChild(el);
      }

This method performs some basic [DOM](https://developer.mozilla.org/en-US/docs/Glossary/DOM) injection; it creates a new [`<p>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p) (paragraph) element, then creates a new [`Text`](https://developer.mozilla.org/en-US/docs/Web/API/Text) node containing the message text, which is received in the event's `data` property. This text node is appended as a child of the new element, which is then inserted into the `receiveBox` block, thereby causing it to draw in the browser window.

### [Disconnecting the peers](#disconnecting_the_peers "Permalink to Disconnecting the peers")

When the user clicks the "Disconnect" button, the `disconnectPeers()` method previously set as that button's handler is called.

      function disconnectPeers() {

        // Close the RTCDataChannels if they're open.

        sendChannel.close();
        receiveChannel.close();

        // Close the RTCPeerConnections

        localConnection.close();
        remoteConnection.close();

        sendChannel = null;
        receiveChannel = null;
        localConnection = null;
        remoteConnection = null;

        // Update user interface elements

        connectButton.disabled = false;
        disconnectButton.disabled = true;
        sendButton.disabled = true;

        messageInputBox.value = "";
        messageInputBox.disabled = true;
      }

This starts by closing each peer's [`RTCDataChannel`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel), then, similarly, each [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection). Then all the saved references to these objects are set to `null` to avoid accidental reuse, and the user interface is updated to reflect the fact that the connection has been closed.

[Next steps](#next_steps "Permalink to Next steps")
---------------------------------------------------

You should <a href="https://mdn-samples.mozilla.org/s/webrtc-simple-datachannel" class="external">try out this example</a> and take a look at the <a href="https://github.com/mdn/samples-server/tree/master/s/webrtc-simple-datachannel" class="external">webrtc-simple-datachannel</a> source code, available on GitHub.

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Signaling and Video Calling](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Signaling_and_video_calling).
-   The [Perfect Negotiation](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Perfect_negotiation) pattern.

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/webrtc_api/simple_rtcdatachannel_sample/index.html "Folder: en-us/web/api/webrtc_api/simple_rtcdatachannel_sample (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWebRTC_API%2FSimple_RTCDataChannel_sample%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fwebrtc_api%2Fsimple_rtcdatachannel_sample%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWebRTC_API%2FSimple_RTCDataChannel_sample%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fwebrtc_api%2Fsimple_rtcdatachannel_sample%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F40b231f5a19b3911305e26907ba7738fde3d31e5%0A*+Document+last+modified%3A+2021-04-06T23%3A51%3A16.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22A+simple+RTCDataChannel+sample%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Apr 6, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Simple_RTCDataChannel_sample/contributors.txt)

Change your languageSelect your preferred language English (US)Português (do Brasil)Русский中文 (简体)

Change language

#### Related Topics

1.  [**WebRTC API**](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API)
2.  WebRTC Guides
    1.  [WebRTC Architecture](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Architecture)
    2.  [WebRTC Basics](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/WebRTC_Basics)
    3.  [WebRTC Protocols](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Protocols)
    4.  [Dealing with connectivity](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Connectivity)
    5.  [Overview of WebRTC interfaces](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Overview)
    6.  [Lifetime of a WebRTC Session](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Session_lifetime)
    7.  [Using data channels](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Using_data_channels)
3.  WebRTC Tutorials
    1.  [Interoperability with adapter.js](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/adapter.js)
    2.  [Taking still photos from the camera](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Taking_still_photos)
    3.  [A simple data channel example](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Simple_RTCDataChannel_sample)
    4.  [Building an internet-connected phone with Peer.js](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Build_a_phone_with_peerjs)
4.  Interfaces
    1.  [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection)
    2.  [`RTCSessionDescription`](https://developer.mozilla.org/en-US/docs/Web/API/RTCSessionDescription)
    3.  [`RTCIceCandidate`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate)
    4.  [`RTCPeerConnectionIceEvent`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnectionIceEvent)
    5.  [`MessageEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MessageEvent)
    6.  [`MediaStream`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream)
    7.  [`RTCStatsReport`](https://developer.mozilla.org/en-US/docs/Web/API/RTCStatsReport)
    8.  [`RTCIdentityEvent`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIdentityEvent)
    9.  [`RTCIdentityErrorEvent`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIdentityErrorEvent)
    10. [`MediaStreamEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamEvent)
    11. [`MediaStreamTrack`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack)
    12. [`MediaDevices`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices)
5.  **[Documentation:](https://developer.mozilla.org/en-US/docs/MDN)**
6.  Contribute
    1.  [The MDN project](https://developer.mozilla.org/en-US/docs/MDN)

-   [Web Technologies](https://developer.mozilla.org/en-US/docs/Web)
-   [Learn Web Development](https://developer.mozilla.org/en-US/docs/Learn)
-   [About MDN](https://developer.mozilla.org/en-US/docs/MDN/About)
-   [Feedback](https://developer.mozilla.org/en-US/docs/MDN/Feedback)

<!-- -->

-   [About](https://www.mozilla.org/about/)
-   [MDN Web Docs Store](https://shop.spreadshirt.com/mdn-store/)
-   [Contact Us](https://www.mozilla.org/contact/)
-   [Firefox](https://www.mozilla.org/firefox/?utm_source=developer.mozilla.org&utm_campaign=footer&utm_medium=referral)

#### MDN

-   <a href="https://twitter.com/mozdevnet" class="social-icon twitter"><span class="visually-hidden">MDN on Twitter</span></a>
-   <a href="https://github.com/mdn/" class="social-icon github"><span class="visually-hidden">MDN on Github</span></a>

#### Mozilla

-   <a href="https://twitter.com/mozilla" class="social-icon twitter"><span class="visually-hidden">Mozilla on Twitter</span></a>
-   <a href="https://www.instagram.com/mozillagram/" class="social-icon instagram"><span class="visually-hidden">Mozilla on Instagram</span></a>

© 2005-2021 Mozilla and individual contributors. Content is available under [these licenses](https://developer.mozilla.org/docs/MDN/About#Copyrights_and_licenses).

-   [Terms](https://www.mozilla.org/about/legal/terms/mozilla)
-   [Privacy](https://www.mozilla.org/privacy/websites/)
-   [Cookies](https://www.mozilla.org/privacy/websites/#cookies)
