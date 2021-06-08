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
4.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Using_DTMF" class="breadcrumb-current-page"><span data-property="name">Using DTMF with WebRTC</span></a>

Table of contents
-----------------

Table of contents

-   [Sending DTMF on an RTCPeerConnection](#sending_dtmf_on_an_rtcpeerconnection)
-   [Simple example](#simple_example)
-   [See also](#see_also)

Using DTMF with WebRTC
======================

<span class="seoSummary">In order to more fully support audio/video conferencing, [WebRTC](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API) supports sending [DTMF](https://developer.mozilla.org/en-US/docs/Glossary/DTMF) to the remote peer on an [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection). This article offers a brief high-level overview of how DTMF works over WebRTC, then provides a guide for everyday developers about how to send DTMF over an `RTCPeerConnection`. The DTMF system is often referred to as "touch tone," after an old trade name for the system.</span>

WebRTC doesn't send DTMF codes as audio data. Instead, they're sent out-of-band, as RTP payloads. Note, however, that although it's possible to *send* DTMF using WebRTC, there is currently no way to detect or receive *incoming* DTMF. WebRTC currently ignores these payloads; this is because WebRTC's DTMF support is primarily intended for use with legacy telephone services that rely on DTMF tones to perform tasks such as:

-   Teleconferencing systems
-   Menu systems
-   Voicemail systems
-   Entry of credit card or other payment information
-   Passcode entry

**Note**: While the DTMF is not sent to the remote peer as audio, browsers may choose to play the corresponding tone to the local user as part of their user experience, since users are typically used to hearing their phone play the tones audibly.

[Sending DTMF on an RTCPeerConnection](#sending_dtmf_on_an_rtcpeerconnection "Permalink to Sending DTMF on an RTCPeerConnection")
---------------------------------------------------------------------------------------------------------------------------------

A given [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection) can have multiple media tracks sent or received on it. When you wish to transmit DTMF signals, you first need to decide which track to send them on, since DTMF is sent as a series of out-of-band payloads on the [`RTCRtpSender`](https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpSender) responsible for transmitting that track's data to the other peer.

Once the track is selected, you can obtain from its `RTCRtpSender` the [`RTCDTMFSender`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDTMFSender) object you'll use for sending DTMF. From there, you can call [`RTCDTMFSender.insertDTMF()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDTMFSender/insertDTMF) to enqueue DTMF signals to be sent on the track to the other peer. The `RTCRtpSender` will then send the tones to the other peer as packets alongside the track's audio data.

Each time a tone is sent, the `RTCPeerConnection` receives a `tonechange` event with a [`tone`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDTMFToneChangeEvent/tone "tone") property specifying which tone finished playing, which is an opportunity to update interface elements, for example. When the tone buffer is empty, indicating that all the tones have been sent, a `tonechange` event with its `tone` property set to "" (an empty string) is delivered to the connection object.

If you'd like to know more about how this works, read <a href="https://tools.ietf.org/html/rfc3550" class="external">RFC 3550: RTP: A Transport Protocol for Real-Time Applications</a> and <a href="https://tools.ietf.org/html/rfc4733" class="external">RFC 4733: RTP Payload for DTMF Digits, Telephony Tones, and Telephony Signals</a>. The details of how DTMF payloads are handled on RTP are beyond the scope of this article. Instead, we'll focus on how to use DTMF within the context of an [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection) by studying how an example works.

[Simple example](#simple_example "Permalink to Simple example")
---------------------------------------------------------------

This simple example constructs two [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection)s, establishes a connection between them, then waits for the user to click a "Dial" button. When the button is clicked, a DTMF string is sent over the connection using [`RTCDTMFSender.insertDTMF()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDTMFSender/insertDTMF). Once the tones finish transmitting, the connection is closed.

**Note**: This example is obviously somewhat contrived, since normally the two `RTCPeerConnection` objects would exist on different devices, and signaling would be done over the network instead of it all being linked up inline as it is here.

### [HTML](#html "Permalink to HTML")

The HTML for this example is very basic; there are only three elements of importance:

-   An [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) element to play the audio received by the `RTCPeerConnection` being "called."
-   A [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button) element to trigger creating and connecting the two `RTCPeerConnection` objects, then sending the DTMF tones.
-   A [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) to receive and display log text to show status information.

<!-- -->

      <p>This example demonstrates the use of DTMF in WebRTC. Note that this
         example is "cheating" by generating both peers in one code stream,
         rather than having each be a truly separate entity.</p>

      <audio id="audio" autoplay controls></audio><br/>
      <button name="dial" id="dial">Dial</button>

      <div class="log"></div>

### [JavaScript](#javascript "Permalink to JavaScript")

Let's take a look at the JavaScript code next. Keep in mind that the process of establishing the connection is somewhat contrived here; you normally don't build both ends of the connection in the same document.

#### Global variables

First, we establish global variables.

    let dialString = "12024561111";

    let callerPC = null;
    let receiverPC = null;
    let dtmfSender = null;

    let hasAddTrack = false;

    let mediaConstraints = {
      audio: true,
      video: false
    };

    let offerOptions = {
      offerToReceiveAudio: 1,
      offerToReceiveVideo: 0
    };

    let dialButton = null;
    let logElement = null;

These are, in order:

`dialString`  
The DTMF string the caller will send when the "Dial" button is clicked.

`callerPC` and `receiverPC`  
The [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection) objects representing the caller and the receiver, respectively. These will be initialized when the call starts up, in our `connectAndDial()` function, as shown in [Starting the connection process](#starting_the_connection_process) below.

`dtmfSender`  
The [`RTCDTMFSender`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDTMFSender) object for the connection. This will be obtained while setting up the connection, in the `gotStream()` function shown in [Adding the audio to the connection](#adding_the_audio_to_the_connection).

`hasAddTrack`  
Because some browsers have not yet implemented [`RTCPeerConnection.addTrack()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/addTrack), therefore requiring the use of the obsolete [`addStream()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/addStream "addStream()") method, we use this Boolean to determine whether or not the user agent supports `addTrack()`; if it doesn't, we'll fall back to `addStream()`. This gets figured out in `connectAndDial()`, as shown in [Starting the connection process](#starting_the_connection_process).

`mediaConstraints`  
An object conforming to the <span class="page-not-created">`MediaConstraints`</span> dictionary specifying the constraints to use when starting the connection. We want an audio-only connection, so `video` is `false`, while `audio` is `true`.

`offerOptions`  
An `RTCOfferOptions` object providing options to specify when calling [`RTCPeerConnection.createOffer()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/createOffer). In this case, we state that we want to receive audio but not video.

`dialButton` and `logElement`  
These variables will be used to store references to the dial button and the [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) into which logging information will be written. They'll get set up when the page is first loaded. See [Initialization](#initialization) below.

#### Initialization

When the page loads, we do some basic setup: we fetch references to the dial button and the log output box elements, and we use [`addEventListener()`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener "addEventListener()") to add an event listener to the dial button so that clicking it calls the `connectAndDial()` function to begin the connection process.

    window.addEventListener("load", function() {
      logElement = document.querySelector(".log");
      dialButton = document.querySelector("#dial");

      dialButton.addEventListener("click", connectAndDial, false);
    });

#### Starting the connection process

When the dial button is clicked, `connectAndDial()` is called. This starts building the WebRTC connection in preparation for sending the DTMF codes.

    function connectAndDial() {
      callerPC = new RTCPeerConnection();

      hasAddTrack = (callerPC.addTrack !== undefined);

      callerPC.onicecandidate = handleCallerIceEvent;
      callerPC.onnegotiationneeded = handleCallerNegotiationNeeded;
      callerPC.oniceconnectionstatechange = handleCallerIceConnectionStateChange;
      callerPC.onsignalingstatechange = handleCallerSignalingStateChangeEvent;
      callerPC.onicegatheringstatechange = handleCallerGatheringStateChangeEvent;

      receiverPC = new RTCPeerConnection();
      receiverPC.onicecandidate = handleReceiverIceEvent;

      if (hasAddTrack) {
        receiverPC.ontrack = handleReceiverTrackEvent;
      } else {
        receiverPC.onaddstream = handleReceiverAddStreamEvent;
      }

      navigator.mediaDevices.getUserMedia(mediaConstraints)
      .then(gotStream)
      .catch(err => log(err.message));
    }

After creating the `RTCPeerConnection` for the caller (`callerPC`), we look to see if it has an [`addTrack()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/addTrack "addTrack()") method. If it does, we set `hasAddTrack` to `true`; otherwise, we set it to `false`. This variable will let the example operate even on browsers not yet implementing the newer `addTrack()` method; we'll do so by falling back to the older [`addStream()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/addStream "addStream()") method.

Next, the event handlers for the caller are established. We'll cover these in detail later.

Then a second `RTCPeerConnection`, this one representing the receiving end of the call, is created and stored in `receiverPC`; its `onicecandidate` event handler is set up too.

If `addTrack()` is supported, we set up the receiver's `ontrack` event handler; otherwise, we set up `onaddstream`. The `track` and `addstream` events are sent when media is added to the connection.

Finally, we call [`getUserMedia()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getUserMedia "getUserMedia()") to obtain access to the caller's microphone. If successful, the function `gotStream()` is called, otherwise we log the error because calling has failed.

#### Adding the audio to the connection

As mentioned above, when the audio input from the microphone is obtained, `gotStream()` is called. Its job is to build the stream being sent to the receiver, so the actual process of starting to transmit can begin. It also gets access to the `RTCDTMFSender` we'll use to issue DTMF on the connection.

    function gotStream(stream) {
      log("Got access to the microphone.");

      let audioTracks = stream.getAudioTracks();

      if (hasAddTrack) {
        if (audioTracks.length > 0) {
          audioTracks.forEach(track => callerPC.addTrack(track, stream));
        }
      } else {
        log("Your browser doesn't support RTCPeerConnection.addTrack(). Falling " +
            "back to the <strong>deprecated</strong> addStream() method...");
        callerPC.addStream(stream);
      }

      if (callerPC.getSenders) {
        dtmfSender = callerPC.getSenders()[0].dtmf;
      } else {
        log("Your browser doesn't support RTCPeerConnection.getSenders(), so " +
            "falling back to use <strong>deprecated</strong> createDTMFSender() " +
            "instead.");
        dtmfSender = callerPC.createDTMFSender(audioTracks[0]);
      }

      dtmfSender.ontonechange = handleToneChangeEvent;
    }

After setting `audioTracks` to be a list of the audio tracks on the stream from the user's microphone, it's time to add the media to the caller's `RTCPeerConnection`. If `addTrack()` is available on the `RTCPeerConnection`, we add each of the stream's audio tracks, one by one, to the connection using [`RTCPeerConnection.addTrack()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/addTrack). Otherwise we call [`RTCPeerConnection.addStream()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/addStream) to add the stream to the call as a single unit.

Next we look to see if the [`RTCPeerConnection.getSenders()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/getSenders) method is implemented. If it is, we call it on `callerPC` and get the first entry in the returned list of senders; this is the [`RTCRtpSender`](https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpSender) responsible for transmitting data for the first audio track on the call (which is the track we'll send DTMF over). We then obtain the `RTCRtpSender`'s [`dtmf`](https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpSender/dtmf "dtmf") property, which is an [`RTCDTMFSender`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDTMFSender) object that can send DTMF on the connection, from the caller to the receiver.

If `getSenders()` isn't available, we instead call <span class="page-not-created">`RTCPeerConnection.createDTMFSender()`</span> to get the `RTCDTMFSender` object. Although this method is obsolete, this example supports it as a fallback to let older browsers (and those not yet updated to support the current WebRTC DTMF API) run the example.

Finally, we set the DTMF sender's [`ontonechange`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDTMFSender/ontonechange "ontonechange") event handler so we get notified each time a DTMF tone finishes playing.

You can find the log function at the bottom of the documentation.

#### When a tone finishes playing

Each time a DTMF tone finishes playing, a `tonechange` event is delivered to `callerPC`. The event listener for these is implemented as the `handleToneChangeEvent()` function.

    function handleToneChangeEvent(event) {
      if (event.tone !== "") {
        log("Tone played: " + event.tone);
      } else {
        log("All tones have played. Disconnecting.");
        callerPC.getLocalStreams().forEach(function(stream) {
          stream.getTracks().forEach(function(track) {
            track.stop();
          });
        });
        receiverPC.getLocalStreams().forEach(function(stream) {
          stream.getTracks().forEach(function(track) {
            track.stop();
          });
        });

        audio.pause();
        audio.srcObject = null;
        receiverPC.close();
        callerPC.close();
      }
    }

The `tonechange` event is used both to indicate when an individual tone has played and when all tones have finished playing. The event's [`tone`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDTMFToneChangeEvent/tone "tone") property is a string indicating which tone just finished playing. If all tones have finished playing, `tone` is an empty string; when that's the case, [`RTCDTMFSender.toneBuffer`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDTMFSender/toneBuffer) is empty.

In this example, we log to the screen which tone just finished playing. In a more advanced application, you might update the user interface, for example, to indicate which note is currently playing.

On the other hand, if the tone buffer is empty, our example is designed to disconnect the call. This is done by stopping each stream on both the caller and the receiver by iterating over each `RTCPeerConnection`'s track list (as returned by its <span class="page-not-created">`getTracks()`</span> method) and calling each track's [`stop()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/stop "stop()") method.

Once both the caller's and the receiver's media tracks are all stopped, we pause the [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) element and set its [`srcObject`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/srcObject "srcObject") to `null`. This detaches the audio stream from the [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) element.

Then, finally, each `RTCPeerConnection` is closed by calling its [`close()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/close "close()") method.

#### Adding candidates to the caller

When the caller's `RTCPeerConnection` ICE layer comes up with a new candidate to propose, it issues an `icecandidate` event to `callerPC`. The `icecandidate` event handler's job is to transmit the candidate to the receiver. In our example, we are directly controlling both the caller and the receiver, so we can just directly add the candidate to the receiver by calling its [`addIceCandidate()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/addIceCandidate "addIceCandidate()") method. That's handled by `handleCallerIceEvent()`:

    function handleCallerIceEvent(event) {
      if (event.candidate) {
        log("Adding candidate to receiver: " + event.candidate.candidate);

        receiverPC.addIceCandidate(new RTCIceCandidate(event.candidate))
        .catch(err => log("Error adding candidate to receiver: " + err));
      } else {
        log("Caller is out of candidates.");
      }
    }

If the `icecandidate` event has a non-`null` `candidate` property, we create a new [`RTCIceCandidate`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate) object from the `event.candidate` string and "transmit" it to the receiver by calling `receiverPC.addIceCandidate()`, providing the new `RTCIceCandidate` as its input. If `addIceCandidate()` fails, the `catch()` clause outputs the error to our log box.

If `event.candidate` is `null`, that indicates that there are no more candidates available, and we log that information.

#### Dialing once the connection is open

Our design requires that when the connection is established, we immediately send the DTMF string. To accomplish that, we watch for the caller to receive an `iceconnectionstatechange` event. This event is sent when one of a number of changes occurs to the state of the ICE connection process, including the successful establishment of a connection.

    function handleCallerIceConnectionStateChange() {
      log("Caller's connection state changed to " + callerPC.iceConnectionState);
      if (callerPC.iceConnectionState === "connected") {
        log("Sending DTMF: \"" + dialString + "\"");
        dtmfSender.insertDTMF(dialString, 400, 50);
      }
    }

The `iceconnectionstatechange` event doesn't actually include within it the new state, so we get the connection process's current state from `callerPC`'s [`RTCPeerConnection.iceConnectionState`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/iceConnectionState) property. After logging the new state, we look to see if the state is `"connected"`. If so, we log the fact that we're about to send the DTMF, then we call [`dtmf.insertDTMF()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDTMFSender/insertDTMF "dtmf.insertDTMF()") to send the DTMF on the same track as the audio data method on the `RTCDTMFSender` object we [previously stored](#adding_the_audio_to_the_connection) in `dtmfSender`.

Our call to `insertDTMF()` specifies not only the DTMF to send (`dialString`), but also the length of each tone in milliseconds (400 ms) and the amount of time between tones (50 ms).

#### Negotiating the connection

When the calling [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection) begins to receive media (after the microphone's stream is added to it), a `negotiationneeded` event is delivered to the caller, letting it know that it's time to start negotiating the connection with the receiver. As previously mentioned, our example is simplified somewhat because we control both the caller and the receiver, so `handleCallerNegotiationNeeded()` is able to quickly construct the connection by chaining the required calls together for both the caller and receiver, as shown below.

    function handleCallerNegotiationNeeded() {
      log("Negotiating...");
      callerPC.createOffer(offerOptions)
      .then(function(offer) {
        log("Setting caller's local description: " + offer.sdp);
        return callerPC.setLocalDescription(offer);
      })
      .then(function() {
        log("Setting receiver's remote description to the same as caller's local");
        return receiverPC.setRemoteDescription(callerPC.localDescription)
      })
      .then(function() {
        log("Creating answer");
        return receiverPC.createAnswer();
      })
      .then(function(answer) {
        log("Setting receiver's local description to " + answer.sdp);
        return receiverPC.setLocalDescription(answer);
      })
      .then(function() {
        log("Setting caller's remote description to match");
        return callerPC.setRemoteDescription(receiverPC.localDescription);
      })
      .catch(err => log("Error during negotiation: " + err.message));
    }

Since the various methods involved in negotiating the connection return [`promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)s, we can chain them together like this:

1.  Call [`callerPC.createOffer()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/createOffer "callerPC.createOffer()") to get an offer.
2.  Then take that offer and set the caller's local description to match by calling [`callerPC.setLocalDescription()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/setLocalDescription "callerPC.setLocalDescription()").
3.  Then "transmit" the offer to the receiver by calling [`receiverPC.setRemoteDescription()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/setRemoteDescription "receiverPC.setRemoteDescription()"). This configures the receiver so that it knows how the caller is configured.
4.  Then the receiver creates an answer by calling [`receiverPC.createAnswer()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/createAnswer "receiverPC.createAnswer()").
5.  Then the receiver sets its local description to match the newly-created answer by calling [`receiverPC.setLocalDescription()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/setLocalDescription "receiverPC.setLocalDescription()").
6.  Then the answer is "transmitted" to the caller by calling [`callerPC.setRemoteDescription()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/setRemoteDescription "callerPC.setRemoteDescription()"). This lets the caller know what the receiver's configuration is.
7.  If at any time an error occurs, the `catch()` clause outputs an error message to the log.

#### Tracking other state changes

We can also watch for changes to the signaling state (by accepting `signalingstatechange` events) and the ICE gathering state (by accepting `icegatheringstatechange` events). We aren't using these for anything, so all we do is log them. We could have not set up these event listeners at all.

    function handleCallerSignalingStateChangeEvent() {
      log("Caller's signaling state changed to " + callerPC.signalingState);
    }

    function handleCallerGatheringStateChangeEvent() {
      log("Caller's ICE gathering state changed to " + callerPC.iceGatheringState);
    }

#### Adding candidates to the receiver

When the receiver's `RTCPeerConnection` ICE layer comes up with a new candidate to propose, it issues an `icecandidate` event to `receiverPC`. The `icecandidate` event handler's job is to transmit the candidate to the caller. In our example, we are directly controlling both the caller and the receiver, so we can just directly add the candidate to the caller by calling its [`addIceCandidate()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/addIceCandidate "addIceCandidate()") method. That's handled by `handleReceiverIceEvent()`.

This code is analogous to the `icecandidate` event handler for the caller, seen in [Adding candidates to the caller](#adding_candidates_to_the_caller) above.

    function handleReceiverIceEvent(event) {
      if (event.candidate) {
        log("Adding candidate to caller: " + event.candidate.candidate);

        callerPC.addIceCandidate(new RTCIceCandidate(event.candidate))
        .catch(err => log("Error adding candidate to caller: " + err));
      } else {
        log("Receiver is out of candidates.");
      }
    }

If the `icecandidate` event has a non-`null` `candidate` property, we create a new [`RTCIceCandidate`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate) object from the `event.candidate` string and deliver it to the caller by passing that into `callerPC.addIceCandidate()`. If `addIceCandidate()` fails, the `catch()` clause outputs the error to our log box.

If `event.candidate` is `null`, that indicates that there are no more candidates available, and we log that information.

#### Adding media to the receiver

When the receiver begins to receive media, an event is delivered to the receiver's [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection), `receiverPC`. As explained in [Starting the connection process](#starting_the_connection_process), the current WebRTC specification uses the `track` event for this, but some browsers haven't been updated to support this yet, so we also need to handle the `addstream` event. The `handleReceiverTrackEvent()` and `handleReceiverAddStreamEvent()` methods, shown below, handle these.

    function handleReceiverTrackEvent(event) {
      audio.srcObject = event.streams[0];
    }

    function handleReceiverAddStreamEvent(event) {
      audio.srcObject = event.stream;
    }

The `track` event includes a [`streams`](https://developer.mozilla.org/en-US/docs/Web/API/RTCTrackEvent/streams "streams") property containing an array of the streams the track is a member of (one track can be part of many streams). We take the first stream and attach it to the [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) element.

The `addstream` event includes a <span class="page-not-created">`stream`</span> property specifying a single stream added to the track. We attach it to the `<audio>` element.

#### Logging

A simple `log()` function is used throughout the code to append HTML to a [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) box for displaying status and errors to the user.

    function log(msg) {
      logElement.innerHTML += msg + "<br/>";
    }

### [Result](#result "Permalink to Result")

You can try this example here. When you click the "Dial" button, you should see a series of logging messages output, then the dialing will begin. If your browser plays the tones audibly as part of its user experience, you should hear them as they're transmitted.

Once transmission of the tones is complete, the connection is closed. You can click "Dial" again to reconnect and send the tones again.

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [WebRTC API](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API)
-   [Lifetime of a WebRTC session](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Session_lifetime)
-   [Signaling and video calling](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Signaling_and_video_calling) (a tutorial and example which explains the signaling process in more detail)
-   [Introduction to WebRTC protocols](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Protocols)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/webrtc_api/using_dtmf/index.html "Folder: en-us/web/api/webrtc_api/using_dtmf (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWebRTC_API%2FUsing_DTMF%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fwebrtc_api%2Fusing_dtmf%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWebRTC_API%2FUsing_DTMF%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fwebrtc_api%2Fusing_dtmf%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Ff6f11d2a249520f01bad93d7c4a5e5cdf6ed914a%0A*+Document+last+modified%3A+2021-02-19T19%3A33%3A30.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22Using+DTMF+with+WebRTC%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Feb 19, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Using_DTMF/contributors.txt)

#### Related Topics

1.  **[WebRTC API](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API)**
2.  **[`WebRTC_API`](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API)**
3.  Related pages for WebRTC
    1.  [`MediaDevices.getUserMedia()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getUserMedia)
    2.  [`Navigator.mediaDevices`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/mediaDevices)
    3.  [`RTCCertificate`](https://developer.mozilla.org/en-US/docs/Web/API/RTCCertificate)
    4.  [`RTCDTMFSender`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDTMFSender)
    5.  [`RTCDTMFToneChangeEvent`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDTMFToneChangeEvent)
    6.  [`RTCDataChannel`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel)
    7.  [`RTCDataChannelEvent`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannelEvent)
    8.  [`RTCDtlsTransport`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDtlsTransport)
    9.  [`RTCErrorEvent`](https://developer.mozilla.org/en-US/docs/Web/API/RTCErrorEvent)
    10. [`RTCIceCandidate`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate)
    11. [`RTCIceTransport`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport)
    12. [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection)
    13. [`RTCPeerConnectionIceErrorEvent`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnectionIceErrorEvent)
    14. [`RTCPeerConnectionIceEvent`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnectionIceEvent)
    15. [`RTCRtpReceiver`](https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpReceiver)
    16. [`RTCRtpSender`](https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpSender)
    17. [`RTCRtpTransceiver`](https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpTransceiver)
    18. [`RTCSctpTransport`](https://developer.mozilla.org/en-US/docs/Web/API/RTCSctpTransport)
    19. [`RTCSessionDescription`](https://developer.mozilla.org/en-US/docs/Web/API/RTCSessionDescription)
    20. [`RTCStatsReport`](https://developer.mozilla.org/en-US/docs/Web/API/RTCStatsReport)
    21. [`RTCTrackEvent`](https://developer.mozilla.org/en-US/docs/Web/API/RTCTrackEvent)

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
