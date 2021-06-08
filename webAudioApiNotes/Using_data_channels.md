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
4.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Using_data_channels" class="breadcrumb-current-page"><span data-property="name">Using WebRTC data channels</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Creating a data channel](#creating_a_data_channel)
-   [Buffering](#buffering)
-   [Understanding message size limits](#understanding_message_size_limits)
-   [Security](#security)

Using WebRTC data channels
==========================

#### Draft

This page is not complete.

Once you've established a WebRTC peer connection using the [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection) interface, you're able to send and receive media data between the two peers on the connection. But there's a lot more you can do with WebRTC. <span class="seoSummary">In this guide, we'll examine how to add a data channel to a peer connection, which can then be used to securely exchange arbitrary data; that is, any kind of data we wish, in any format we choose.</span>

Since all WebRTC components are required to use encryption, any data transmitted on an `RTCDataChannel` is automatically secured using Datagram Transport Layer Security (**DTLS**). See [Security](#security) below for more information.

[Creating a data channel](#creating_a_data_channel "Permalink to Creating a data channel")
------------------------------------------------------------------------------------------

The underlying data transport used by the [`RTCDataChannel`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel) can be created in one of two ways:

-   Let WebRTC create the transport and announce it to the remote peer for you (by causing it to receive a `datachannel` event). This is the easy way, and works for a wide variety of use cases, but may not be flexible enough for your needs.
-   Write your own code to negotiate the data transport and write your own code to signal to the other peer that it needs to connect to the new channel.

Let's look at each of these cases, starting with the first, which is the most common.

### [Automatic negotiation](#automatic_negotiation "Permalink to Automatic negotiation")

Often, you can allow the peer connection to handle negotiating the [`RTCDataChannel`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel) connection for you. To do this, call

[`createDataChannel()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/createDataChannel "createDataChannel()") without specifying a value for the <span class="page-not-created">`negotiated`</span> property, or specifying the property with a value of `false`. This will automatically trigger the `RTCPeerConnection` to handle the negotiations for you, causing the remote peer to create a data channel and linking the two together across the network.

The `RTCDataChannel` object is returned immediately by `createDataChannel()`; you can tell when the connection has been made successfully by watching for the [`open`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/open_event "open") event to be sent to the `RTCDataChannel`.

    let dataChannel = pc.createDataChannel("MyApp Channel");

    dataChannel.addEventListener("open", (event) => {
      beginTransmission(dataChannel);
    });

### [Manual negotiation](#manual_negotiation "Permalink to Manual negotiation")

To manually negotiate the data channel connection, you need to first create a new [`RTCDataChannel`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel) object using the [`createDataChannel()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/createDataChannel "createDataChannel()") method on the [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection), specifying in the options a <span class="page-not-created">`negotiated`</span> property set to `true`. This signals to the peer connection to not attempt to negotiate the channel on your behalf.

Then negotiate the connection out-of-band, using a web server or other means. This process should signal to the remote peer that it should create its own `RTCDataChannel` with the `negotiated` property also set to `true`, using the same [`id`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/id "id"). This will link the two objects across the `RTCPeerConnection`.

    let dataChannel = pc.createDataChannel("MyApp Channel", {
      negotiated: true
    });

    dataChannel.addEventListener("open", (event) => {
      beginTransmission(dataChannel);
    });

    requestRemoteChannel(dataChannel.id);

In this code snippet, the channel is created with `negotiated` set to `true`, then a function called `requestRemoteChannel()` is used to trigger negotiation, to create a remote channel with the same ID as the local channel.

Doing this lets you create data channels with each peer using different properties, and to create channels declaratively by using the same value for `id`.

[Buffering](#buffering "Permalink to Buffering")
------------------------------------------------

WebRTC data channels support buffering of outbound data. This is handled automatically. While there's no way to control the size of the buffer, you can learn how much data is currently buffered, and you can choose to be notified by an event when the buffer starts to run low on queued data. This makes it easy to write efficient routines that make sure there's always data ready to send without over-using memory or swamping the channel completely.

**&lt;&lt;&lt;write more about using bufferedAmount, bufferedAmountLowThreshold, onbufferedamountlow, and bufferedamountlow here&gt;&gt;&gt;**

...

[Understanding message size limits](#understanding_message_size_limits "Permalink to Understanding message size limits")
------------------------------------------------------------------------------------------------------------------------

For any data being transmitted over a network, there are size restrictions. At a fundamental level, the individual network packets can't be larger than a certain value (the exact number depends on the network and the transport layer being used). At the application level—that is, within the [user agent's](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) implementation of WebRTC on which your code is running—the WebRTC implementation implements features to support messages that are larger than the maximum packet size on the network's transport layer.

This can complicate things, since you don't necessarily know what the size limits are for various user agents, and how they respond when a larger message is sent or received. Even when user agents share the same underlying library for handling Stream Control Transmission Protocol (SCTP) data, there can still be variations due to how the library is used. For example, both Firefox and Google Chrome use the `usrsctp` library to implement SCTP, but there are still situations in which data transfer on an `RTCDataChannel` can fail due to differences in how they call the library and react to errors it returns.

When two users running Firefox are communicating on a data channel, the message size limit is much larger than when Firefox and Chrome are communicating because Firefox implements a now deprecated technique for sending large messages in multiple SCTP messages, which Chrome does not. Chrome will instead see a series of messages that it believes are complete, and will deliver them to the receiving `RTCDataChannel` as multiple messages.

Messages smaller than 16kiB can be sent without concern, as all major user agents handle them the same way. Beyond that, things get more complicated.

### [Concerns with large messages](#concerns_with_large_messages "Permalink to Concerns with large messages")

Currently, it's not practical to use `RTCDataChannel` for messages larger than 64kiB (16kiB if you want to support cross-browser exchange of data). The problem arises from the fact that SCTP—the protocol used for sending and receiving data on an `RTCDataChannel`—was originally designed for use as a signaling protocol. It was expected that messages would be relatively small. Support for messages larger than the network layer's <a href="https://en.wikipedia.org/wiki/Maximum_transmission_unit" class="external" title="MTU">MTU</a> was added almost as an afterthought, in case signaling messages needed to be larger than the MTU. This feature requires that each piece of the message have consecutive sequence numbers, so they have to be transmitted one after another, without any other data interleaved between them.

This eventually became a problem. Over time, various applications (including those implementing WebRTC) began to use SCTP to transmit larger and larger messages. Eventually it was realized that when the messages become too large, it's possible for the transmission of a large message to block all other data transfers on that data channel—including critical signaling messages.

This will become an issue when browsers properly support the current standard for supporting larger messages—the end-of-record (EOR) flag that indicates when a message is the last one in a series that should be treated as a single payload. This is implemented in Firefox 57, but is not yet implemented in Chrome (see <a href="https://bugs.chromium.org/p/webrtc/issues/detail?id=7774" class="external">Chromium Bug 7774</a>). With EOR support in place, `RTCDataChannel` payloads can be much larger (officially up to 256kiB, but Firefox's implementation caps them at a whopping 1GiB). Even at 256kiB, that's large enough to cause noticeable delays in handling urgent traffic. If you go even larger, the delays can become untenable unless you are certain of your operational conditions.

In order to resolve this issue, a new system of **stream schedulers** (usually referred to as the "SCTP ndata specification") has been designed to make it possible to interleave messages sent on different streams, including streams used to implement WebRTC data channels. This <a href="https://datatracker.ietf.org/doc/html/draft-ietf-tsvwg-sctp-ndata" class="external">proposal</a> is still in IETF draft form, but once implemented, it will make it possible to send messages with essentially no size limitations, since the SCTP layer will automatically interleave the underlying sub-messages to ensure that every channel's data has the opportunity to get through.

Firefox support for ndata is in the process of being implemented; see <a href="https://bugzilla.mozilla.org/show_bug.cgi?id=1381145" class="external">bug 1381145</a> to track it becoming available for general use. The Chrome team is tracking their implementation of ndata support in <a href="https://bugs.chromium.org/p/webrtc/issues/detail?id=5696" class="external">Chrome Bug 5696</a>.

Much of the information in this section is based in part on the blog post <a href="https://lgrahl.de/articles/demystifying-webrtc-dc-size-limit.html" class="external">Demystifyijng WebRTC's Data Channel Message Size Limitations</a>, written by Lennart Grahl. He goes into a bit more detail there, but as browsers have been updated since then some of it may be out-of-date. In addition, as time goes by, it will become more so, especially once EOR and ndata support are fully integrated in the major browsers.

[Security](#security "Permalink to Security")
---------------------------------------------

All data transferred using WebRTC is encrypted. In the case of `RTCDataChannel`, the encryption used is Datagram Transport Layer Security (DTLS), which is based on [Transport Layer Security](https://developer.mozilla.org/en-US/docs/Web/Security/Transport_Layer_Security) (TLS). Since TLS is used to secure every HTTPS connection, any data you send on a data channel is as secure as any other data sent or received by the user's browser.

More fundamentally, since WebRTC is a peer-to-peer connection between two user agents, the data never passes through the web or application server. This reduces opportunities to have the data intercepted.

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/webrtc_api/using_data_channels/index.html "Folder: en-us/web/api/webrtc_api/using_data_channels (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWebRTC_API%2FUsing_data_channels%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fwebrtc_api%2Fusing_data_channels%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWebRTC_API%2FUsing_data_channels%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fwebrtc_api%2Fusing_data_channels%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F48fca0c614add538e95f1075b2777fc396023d31%0A*+Document+last+modified%3A+2021-03-16T07%3A50%3A01.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22Using+WebRTC+data+channels%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Mar 16, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Using_data_channels/contributors.txt)

Change your languageSelect your preferred language English (US)한국어Русский

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
