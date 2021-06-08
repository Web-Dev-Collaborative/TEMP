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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection" class="breadcrumb-penultimate"><span data-property="name">RTCPeerConnection</span></a>
4.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/icecandidateerror_event" class="breadcrumb-current-page"><span data-property="name">RTCPeerConnection: icecandidateerror event</span></a>

Table of contents
-----------------

Table of contents

-   [Description](#description)
-   [Example](#example)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)

RTCPeerConnection: icecandidateerror event
==========================================

The [WebRTC API](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API) event `icecandidateerror` is sent to an [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection) if an error occurs while performing ICE negotiations through a [STUN](https://developer.mozilla.org/en-US/docs/Glossary/STUN) or [TURN](https://developer.mozilla.org/en-US/docs/Glossary/TURN) server. The event object is of type [`RTCPeerConnectionIceErrorEvent`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnectionIceErrorEvent), and contains information describing the error in some amount of detail.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnectionIceErrorEvent"><code>RTCPeerConnectionIceErrorEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/onicecandidateerror"><code>RTCPeerConnection.onicecandidateerror</code></a></td></tr></tbody></table>

[Description](#description "Permalink to Description")
------------------------------------------------------

The error object's <span class="page-not-created">`errorCode`</span> property is one of the numeric STUN error codes. There is one additional, WebRTC-specific, error which lies outside the valid STUN error code range: 701. Error 701 indicates that none of the ICE candidates were able to successfully make contact with the STUN or TURN server.

The 701 error is fired only once per server URL from the list of available STUN or TURN servers provided when creating the [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection). These errors occur only when the connection's [ICE gathering state](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/iceGatheringState) is `gathering`.

[Example](#example "Permalink to Example")
------------------------------------------

The following example establishes a handler for `icecandidateerror`s that occur on the [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection) `pc`. This handler looks specifically for 701 errors that indicate that candidates couldn't reach the STUN or TURN server.

When this happens, the server URL and the error message are passed to a function called `reportConnectFail()` to log or output the connection failure.

    pc.addEventListener("icecandidateerror", (event) => {
      if (event.errorCode === 701) {
        reportConnectFail(event.url, event.errorText);
      }
    });

Note that if multiple STUN and/or TURN servers are provided when creating the connection, this error may happen more than once, if more than one of those servers fails. Each provided server is tried until a connection is established.

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#event-icecandidateerror" class="external">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'icecandidateerror' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

No compatibility data found for `api.RTCPeerConnection.icecandidateerror_event`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/rtcpeerconnection/icecandidateerror_event/index.html "Folder: en-us/web/api/rtcpeerconnection/icecandidateerror_event (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FRTCPeerConnection%2Ficecandidateerror_event%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Frtcpeerconnection%2Ficecandidateerror_event%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FRTCPeerConnection%2Ficecandidateerror_event%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Frtcpeerconnection%2Ficecandidateerror_event%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fb38887c5d8925adbfe4c051f5e59132c7363f55a%0A*+Document+last+modified%3A+2021-05-31T16%3A07%3A26.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22RTCPeerConnection%3A+icecandidateerror+event%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/icecandidateerror_event/contributors.txt)

#### Related Topics

1.  **[WebRTC API](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API)**
2.  Guides
    1.  [Introduction to WebRTC protocols](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Protocols)
    2.  [WebRTC connectivity](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Connectivity)
    3.  [Lifetime of a WebRTC session](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Session_lifetime)
    4.  [Signaling and video calling](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Signaling_and_video_calling)
    5.  [Using WebRTC data channels](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Using_data_channels)
    6.  [Using DTMF with WebRTC](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Using_DTMF)
    7.  [Improving compatibility using WebRTC adapter.js](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/adapter.js)
    8.  [Taking still photos with WebRTC](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Taking_still_photos)
    9.  [A simple RTCDataChannel sample](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Simple_RTCDataChannel_sample)
3.  Interfaces
    1.  [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection)
    2.  [`RTCSessionDescription`](https://developer.mozilla.org/en-US/docs/Web/API/RTCSessionDescription)
    3.  [`RTCIceCandidate`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate)
    4.  [`RTCPeerConnectionIceEvent`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnectionIceEvent)
    5.  [`RTCPeerConnectionIceErrorEvent`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnectionIceErrorEvent)
    6.  [`RTCCertificate`](https://developer.mozilla.org/en-US/docs/Web/API/RTCCertificate)
    7.  [`RTCRtpSender`](https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpSender)
    8.  [`RTCRtpReceiver`](https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpReceiver)
    9.  [`RTCRtpTransceiver`](https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpTransceiver)
    10. [`RTCDtlsTransport`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDtlsTransport)
    11. [`RTCIceTransport`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport)
    12. [`RTCTrackEvent`](https://developer.mozilla.org/en-US/docs/Web/API/RTCTrackEvent)
    13. [`RTCSctpTransport`](https://developer.mozilla.org/en-US/docs/Web/API/RTCSctpTransport)
    14. [`RTCDataChannel`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel)
    15. [`RTCDataChannelEvent`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannelEvent)
    16. [`RTCDTMFSender`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDTMFSender)
    17. [`RTCDTMFToneChangeEvent`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDTMFToneChangeEvent)
    18. [`RTCStatsReport`](https://developer.mozilla.org/en-US/docs/Web/API/RTCStatsReport)
    19. [`RTCErrorEvent`](https://developer.mozilla.org/en-US/docs/Web/API/RTCErrorEvent)
4.  Properties
    1.  [`Navigator.mediaDevices`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/mediaDevices)
5.  Methods
    1.  [`MediaDevices.getUserMedia()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getUserMedia)
6.  Events
    1.  [`RTCDTMFSender`: `tonechange`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDTMFSender/tonechange_event)
    2.  [`RTCDataChannel`: `bufferedamountlow`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/bufferedamountlow_event)
    3.  [`RTCDataChannel`: `close`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/close_event)
    4.  [`RTCDataChannel`: `closing`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/closing_event)
    5.  [`RTCDataChannel`: `error`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/error_event)
    6.  [`RTCDataChannel`: `message`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/message_event)
    7.  [`RTCDataChannel`: `open`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/open_event)
    8.  [`RTCDtlsTransport`: `error`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDtlsTransport/error_event)
    9.  [`RTCDtlsTransport`: `statechange`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDtlsTransport/statechange_event)
    10. [`RTCIceTransport`: `error`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/error_event)
    11. [`RTCIceTransport`: `gatheringstatechange`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/gatheringstatechange_event)
    12. [`RTCIceTransport`: `selectedcandidatepairchange`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/selectedcandidatepairchange_event)
    13. [`RTCIceTransport`: `statechange`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/statechange_event)
    14. [`RTCPeerConnection`: `connectionstatechange`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/connectionstatechange_event)
    15. [`RTCPeerConnection`: `datachannel`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/datachannel_event)
    16. [`RTCPeerConnection`: `icecandidate`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/icecandidate_event)
    17. [`RTCPeerConnection`: `icecandidateerror`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/icecandidateerror_event)
    18. [`RTCPeerConnection`: `iceconnectionstatechange`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/iceconnectionstatechange_event)
    19. [`RTCPeerConnection`: `icegatheringstatechange`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/icegatheringstatechange_event)
    20. [`RTCPeerConnection`: `negotiationneeded`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/negotiationneeded_event)
    21. [`RTCPeerConnection`: `signalingstatechange`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/signalingstatechange_event)
    22. [`RTCPeerConnection`: `track`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/track_event)
    23. [`RTCSctpTransport`: `error`](https://developer.mozilla.org/en-US/docs/Web/API/RTCSctpTransport/error_event)

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
