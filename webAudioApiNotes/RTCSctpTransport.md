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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCSctpTransport" class="breadcrumb-current-page"><span data-property="name">RTCSctpTransport</span></a>

Table of contents
-----------------

Table of contents

-   [Properties](#properties)
-   [Methods](#methods)
-   [Example](#example)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

RTCSctpTransport
================

#### Experimental

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The **`RTCSctpTransport`** interface provides information which describes a Stream Control Transmission Protocol (**[SCTP](https://developer.mozilla.org/en-US/docs/Glossary/SCTP)**) transport. This provides information about limitations of the transport, but also provides a way to access the underlying Datagram Transport Layer Security (**[DTLS](https://developer.mozilla.org/en-US/docs/Glossary/DTLS)**) transport over which SCTP packets for all of an [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection)'s data channels are sent and received.

You don't create [`RTCSctpTransport`](https://developer.mozilla.org/en-US/docs/Web/API/RTCSctpTransport) objects yourself; instead, you get access to the `RTCSctpTransport` for a given `RTCPeerConnection` through its **[`sctp`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/sctp "sctp")** property.

Possibly the most useful property on this interface is its <span class="page-not-created">`maxMessageSize`</span> property, which you can use to determine the upper limit on the size of messages you can send over a data channel on the peer connection.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

*Also inherits properties from: [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)*

<span class="page-not-created">`RTCSctpTransport.maxChannels`</span><span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
An integer value indicating the maximum number of [`RTCDataChannel`s](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel "<code>RTCDataChannel</code>s") that can be open simultaneously.

<span class="page-not-created">`RTCSctpTransport.maxMessageSize`</span><span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
An integer value indicating the maximum size, in bytes, of a message which can be sent using the [`RTCDataChannel.send()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/send) method.

[`RTCSctpTransport.state`](https://developer.mozilla.org/en-US/docs/Web/API/RTCSctpTransport/state)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) enumerated value indicating the state of the SCTP transport.

<span class="page-not-created">`RTCSctpTransport.transport`</span><span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
An [`RTCDtlsTransport`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDtlsTransport) object representing the [DTLS](https://developer.mozilla.org/en-US/docs/Glossary/DTLS) transport used for the transmission and receipt of data packets.

### [Event handlers](#event_handlers "Permalink to Event handlers")

<span class="page-not-created">`RTCSctpTransport.onstatechange`</span>  
Fired when the [`RTCSctpTransport.state`](https://developer.mozilla.org/en-US/docs/Web/API/RTCSctpTransport/state) changes.

[Methods](#methods "Permalink to Methods")
------------------------------------------

*This interface has no methods, but inherits methods from: [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)*

[Example](#example "Permalink to Example")
------------------------------------------

TBD

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#rtcsctptransport-interface" class="external">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCSctpTransport' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [WebRTC](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API)
-   [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection)
-   [`RTCPeerConnection.sctp`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/sctp)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/rtcsctptransport/index.html "Folder: en-us/web/api/rtcsctptransport (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FRTCSctpTransport%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Frtcsctptransport%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FRTCSctpTransport%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Frtcsctptransport%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fb38887c5d8925adbfe4c051f5e59132c7363f55a%0A*+Document+last+modified%3A+2021-05-31T16%3A07%3A26.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22RTCSctpTransport%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/RTCSctpTransport/contributors.txt)

#### Related Topics

1.  **[WebRTC API](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API)**
2.  **[`RTCSctpTransport`](https://developer.mozilla.org/en-US/docs/Web/API/RTCSctpTransport)**
3.  Properties
    1.  [`state`](https://developer.mozilla.org/en-US/docs/Web/API/RTCSctpTransport/state)
4.  Related pages for WebRTC
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