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
2.  <a href="https://developer.mozilla.org/en-US/docs/Web/API" class="breadcrumb-penultimate"><span data-property="name">Web APIs</span></a>
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel" class="breadcrumb-current-page"><span data-property="name">RTCDataChannel</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Properties](#properties)
-   [Events](#events)
-   [Data format](#data_format)
-   [Example](#example)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

RTCDataChannel
==============

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

The **`RTCDataChannel`** interface represents a network channel which can be used for bidirectional peer-to-peer transfers of arbitrary data. Every data channel is associated with an [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection), and each peer connection can have up to a theoretical maximum of 65,534 data channels (the actual limit may vary from browser to browser).

To create a data channel and ask a remote peer to join you, call the [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection)'s [`createDataChannel()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/createDataChannel "createDataChannel()") method. The peer being invited to exchange data receives a `datachannel` event (which has type [`RTCDataChannelEvent`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannelEvent)) to let it know the data channel has been added to the connection.

*Also inherits properties from: [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)*

[`binaryType`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/binaryType)   
The property `binaryType` on the `RTCDataChannel` interface is a `DOMString` which specifies the type of JavaScript object which should be used to represent binary data received on the `RTCDataChannel`. Values allowed by the `WebSocket.binaryType` property are also permitted here: `"blob"` if `Blob` objects are being used or `"arraybuffer"` if `ArrayBuffer` objects are being used. The default is `"blob"`.

[`bufferedAmount`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/bufferedAmount) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
The read-only `RTCDataChannel` property `bufferedAmount` returns the number of bytes of data currently queued to be sent over the data channel.

[`bufferedAmountLowThreshold`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/bufferedAmountLowThreshold)   
The `RTCDataChannel` property `bufferedAmountLowThreshold` is used to specify the number of bytes of buffered outgoing data that is considered "low." The default value is 0.

[`id`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/id) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
The read-only `RTCDataChannel` property `id` returns an ID number (between 0 and 65,534) which uniquely identifies the `RTCDataChannel`.

[`label`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/label) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
The read-only `RTCDataChannel` property `label` returns a `DOMString` containing a name describing the data channel. These labels are not required to be unique.

[`maxPacketLifeTime`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/maxPacketLifeTime) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
The read-only `RTCDataChannel` property `maxPacketLifeTime` returns the amount of time, in milliseconds, the browser is allowed to take to attempt to transmit a message, as set when the data channel was created, or `null`.

[`maxRetransmits`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/maxRetransmits) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
The read-only `RTCDataChannel` property `maxRetransmits` returns the maximum number of times the browser should try to retransmit a message before giving up, as set when the data channel was created, or `null`, which indicates that there is no maximum.

[`negotiated`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/negotiated) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
The read-only `RTCDataChannel` property `negotiated` indicates whether the `RTCDataChannel`'s connection was negotiated by the Web app (`true`) or by the WebRTC layer (`false`).

[`ordered`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/ordered) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
The read-only `RTCDataChannel` property `ordered` indicates whether or not the data channel guarantees in-order delivery of messages; the default is `true`, which indicates that the data channel is indeed ordered.

[`protocol`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/protocol) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
The read-only `RTCDataChannel` property `protocol` returns a `DOMString` containing the name of the subprotocol in use. If no protocol was specified when the data channel was created, then this property's value is "" (the empty string).

[`readyState`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/readyState) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
The read-only `RTCDataChannel` property `readyState` returns an enum of type `RTCDataChannelState` which indicates the state of the data channel's underlying data connection.

[`reliable`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/reliable) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
The read-only `RTCDataChannel` property `reliable` indicates whether or not the data channel is reliable.

[`stream`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/stream) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
The deprecated (and never part of the official specification) read-only `RTCDataChannel` property `stream` returns an ID number (between 0 and 65,535) which uniquely identifies the `RTCDataChannel`.

[`onbufferedamountlow`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/onbufferedamountlow)   
The **`RTCDataChannel.onbufferedamountlow`** property is an `Event_handlers` which specifies a function the browser calls when the `bufferedamountlow` event is sent to the `RTCDataChannel`. This event, which is represented by a simple `Event` object, is sent when the amount of data buffered to be sent falls to or below the threshold specified by the channel's `RTCDataChannel.bufferedAmountLowThreshold`.

[`onclose`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/onclose)   
The `RTCDataChannel.onclose` property is an `Event_handlers` which specifies a function to be called by the browser when the `close` event is received by the `RTCDataChannel`. This is a simple `Event` which indicates that the data channel has closed down.

[`onclosing`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/onclosing)   
The `RTCDataChannel.onclosing` property is an `Event_handlers` which specifies a function to be called by the browser when the `closing` event is received by the `RTCDataChannel`. This is a simple `Event` which indicates that the data channel is being closed, that is, `RTCDataChannel` transitions to "closing" state. For example, after `RTCDataChannel.close` was called but the underlying data transport might not have been closed yet.

[`onerror`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/onerror)   
The `RTCDataChannel.onerror` property is an `Event_handlers` which specifies a function to be called when the `error` event is received. When an error occurs on the data channel, the function receives as input an `ErrorEvent` object describing the error which occurred.

[`onmessage`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/onmessage)   
The `RTCDataChannel.onmessage` property stores an `Event_handlers` which specifies a function to be called when the `message` event is fired on the channel. This event is represented by the `MessageEvent` interface. This event is sent to the channel when a message is received from the other peer.

[`onopen`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/onopen)   
The `RTCDataChannel.onopen` property is an `Event_handlers` which specifies a function to be called when the `open` event is fired; this is a simple `Event` which is sent when the data channel's underlying data transport—the link over which the `RTCDataChannel`'s messages flow—is established or re-established.

[`close()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/close)  
The `RTCDataChannel.close()` method closes the `RTCDataChannel`. Either peer is permitted to call this method to initiate closure of the channel.

[`send()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/send)  
The `send()` method of the `RTCDataChannel` interface sends data across the data channel to the remote peer.

[Events](#events "Permalink to Events")
---------------------------------------

[`bufferedamountlow`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/bufferedamountlow_event "bufferedamountlow")  
Sent to the channel's [`onbufferedamountlow`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/onbufferedamountlow "onbufferedamountlow") event handler when the number of bytes of data in the outgoing data buffer falls below the value specified by [`bufferedAmountLowThreshold`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/bufferedAmountLowThreshold "bufferedAmountLowThreshold").

[`close`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/close_event "close")  
Sent to the [`onclose`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/onclose "onclose") event handler when the underlying data transport closes.

[`error`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/error_event "error")  
Sent to the [`onerror`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/onerror "onerror") event handler when an error occurs on the data channel.

[`message`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/message_event "message")  
Sent to the [`onmessage`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/onmessage "onmessage") event handler when a message has been received from the remote peer. The message contents can be found in the event's [`data`](https://developer.mozilla.org/en-US/docs/Web/API/MessageEvent/data "data") property.

[`open`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/open_event "open")  
Sent to the [`onopen`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/onopen "onopen") event handler when the data channel is first opened, or when an existing data channel's underlying connection re-opens.

[Data format](#data_format "Permalink to Data format")
------------------------------------------------------

The underlying data format is defined by the IEEE draft specification `draft-ietf-mmusic-sctp-sdp`. The current format specifies its protocol as either `"UDP/DTLS/SCTP"` (UDP carrying DTLS carrying SCTP) or `"TCP/DTLS/SCTP"` (TCP carrying DTLS carrying SCTP). Older browsers may only specify `"DTLS/SCTP"`.

[Example](#example "Permalink to Example")
------------------------------------------

    var pc = new RTCPeerConnection();
    var dc = pc.createDataChannel("my channel");

    dc.onmessage = function (event) {
      console.log("received: " + event.data);
    };

    dc.onopen = function () {
      console.log("datachannel open");
    };

    dc.onclose = function () {
      console.log("datachannel close");
    };

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#rtcdatachannel" class="external">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCDataChannel' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/API/WebRTC_API" class="page-not-created" title="This is a link to an unwritten page">WebRTC API</a>

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/rtcdatachannel/index.html "Folder: en-us/web/api/rtcdatachannel (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FRTCDataChannel%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Frtcdatachannel%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FRTCDataChannel%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Frtcdatachannel%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fb38887c5d8925adbfe4c051f5e59132c7363f55a%0A*+Document+last+modified%3A+2021-05-31T16%3A07%3A26.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22RTCDataChannel%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/contributors.txt)

Change your languageSelect your preferred language English (US)日本語Português (do Brasil)中文 (简体)

Change language

#### Related Topics

1.  **[WebRTC API](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API)**
2.  **[`RTCDataChannel`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel)**
3.  Properties
    1.  [`binaryType`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/binaryType)
    2.  [`bufferedAmount`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/bufferedAmount)
    3.  [`bufferedAmountLowThreshold`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/bufferedAmountLowThreshold)
    4.  [`id`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/id)
    5.  [`label`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/label)
    6.  [`maxPacketLifeTime`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/maxPacketLifeTime)
    7.  [`maxRetransmits`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/maxRetransmits)
    8.  [`negotiated`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/negotiated)
    9.  [`onbufferedamountlow`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/onbufferedamountlow)
    10. [`onclose`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/onclose)
    11. [`onclosing`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/onclosing)
    12. [`onerror`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/onerror)
    13. [`onmessage`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/onmessage)
    14. [`onopen`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/onopen)
    15. [`ordered`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/ordered)
    16. [`protocol`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/protocol)
    17. [`readyState`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/readyState)
    18. [`reliable`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/reliable)
    19. [`stream`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/stream)
4.  Methods
    1.  [`close()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/close)
    2.  [`send()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/send)
5.  Inheritance:
    1.  [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)
6.  Related pages for WebRTC
    1.  [`MediaDevices.getUserMedia()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getUserMedia)
    2.  [`Navigator.mediaDevices`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/mediaDevices)
    3.  [`RTCCertificate`](https://developer.mozilla.org/en-US/docs/Web/API/RTCCertificate)
    4.  [`RTCDTMFSender`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDTMFSender)
    5.  [`RTCDTMFToneChangeEvent`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDTMFToneChangeEvent)
    6.  [`RTCDataChannelEvent`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannelEvent)
    7.  [`RTCDtlsTransport`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDtlsTransport)
    8.  [`RTCErrorEvent`](https://developer.mozilla.org/en-US/docs/Web/API/RTCErrorEvent)
    9.  [`RTCIceCandidate`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate)
    10. [`RTCIceTransport`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport)
    11. [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection)
    12. [`RTCPeerConnectionIceErrorEvent`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnectionIceErrorEvent)
    13. [`RTCPeerConnectionIceEvent`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnectionIceEvent)
    14. [`RTCRtpReceiver`](https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpReceiver)
    15. [`RTCRtpSender`](https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpSender)
    16. [`RTCRtpTransceiver`](https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpTransceiver)
    17. [`RTCSctpTransport`](https://developer.mozilla.org/en-US/docs/Web/API/RTCSctpTransport)
    18. [`RTCSessionDescription`](https://developer.mozilla.org/en-US/docs/Web/API/RTCSessionDescription)
    19. [`RTCStatsReport`](https://developer.mozilla.org/en-US/docs/Web/API/RTCStatsReport)
    20. [`RTCTrackEvent`](https://developer.mozilla.org/en-US/docs/Web/API/RTCTrackEvent)

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
