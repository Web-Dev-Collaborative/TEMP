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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate" class="breadcrumb-current-page"><span data-property="name">RTCIceCandidate</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Constructor](#constructor)
-   [Properties](#properties)
-   [Methods](#methods)
-   [Examples](#examples)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)

RTCIceCandidate
===============

<span class="seoSummary">The **`RTCIceCandidate`** interface—part of the [WebRTC API](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API)—represents a candidate Internet Connectivity Establishment ([ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE)) configuration which may be used to establish an [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection).</span>

An ICE candidate describes the protocols and routing needed for WebRTC to be able to communicate with a remote device. When starting a WebRTC peer connection, typically a number of candidates are proposed by each end of the connection, until they mutually agree upon one which describes the connection they decide will be best. WebRTC then uses that candidate's details to initiate the connection.

For details on how the ICE process works, see [Lifetime of a WebRTC session](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Session_lifetime). The article [WebRTC connectivity](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Connectivity) provides additional useful details.

[Constructor](#constructor "Permalink to Constructor")
------------------------------------------------------

[`RTCIceCandidate()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/RTCIceCandidate "RTCIceCandidate()")  
Creates an `RTCIceCandidate` object to represent a single ICE candidate, optionally configured based on an object based on the [`RTCIceCandidateInit`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidateInit) dictionary.

**Note:** For backward compatibility, the constructor also accepts as input a string containing the value of the [`candidate`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/candidate "candidate") property instead of a [`RTCIceCandidateInit`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidateInit) object, since the `candidate` includes all of the information that `RTCIceCandidateInit` does and more.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

[`candidate`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/candidate "candidate") <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) representing the transport address for the candidate that can be used for connectivity checks. The format of this address is a `candidate-attribute` as defined in <a href="https://tools.ietf.org/html/rfc5245" class="external">RFC 5245</a>. This string is empty (`""`) if the `RTCIceCandidate` is an "end of candidates" indicator.

[`component`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/component "component") <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) which indicates whether the candidate is an RTP or an RTCP candidate; its value is either `"rtp"` or `"rtcp"`, and is derived from the  `"component-id"` field in the `candidate` a-line string. The permitted values are listed in the [`RTCIceComponent`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceComponent) enumerated type.

[`foundation`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/foundation "foundation") <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) containing a unique identifier that is the same for any candidates of the same type, share the same base (the address from which the ICE agent sent the candidate), and come from the same [STUN](https://developer.mozilla.org/en-US/docs/Glossary/STUN) server. This is used to help optimize ICE performance while prioritizing and correlating candidates that appear on multiple [`RTCIceTransport`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport) objects.

[`ip`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/address "ip") <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) containing the IP address of the candidate.

[`port`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/port "port") <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
An integer value indicating the candidate's port number.

[`priority`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/priority "priority") <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
A long integer value indicating the candidate's priority.

[`address`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/address "address") <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
The address of the candidate.

[`protocol`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/protocol "protocol") <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
A string indicating whether the candidate's protocol is `"tcp"` or `"udp"`. The string is one of those in the enumerated type `RTCIceProtocol`.

[`relatedAddress`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/relatedAddress "relatedAddress") <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
If the candidate is derived from another candidate, `relatedAddress` is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) containing that host candidate's IP address. For host candidates, this value is `null`.

[`relatedPort`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/relatedPort "relatedPort") <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
For a candidate that is derived from another, such as a relay or reflexive candidate, the `relatedPort` is a number indicating the port number of the candidate from which this candidate is derived. For host candidates, the `relatedPort` property is `null`.

[`sdpMid`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/sdpMid "sdpMid") <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) specifying the candidate's media stream identification tag which uniquely identifies the media stream within the component with which the candidate is associated, or `null` if no such association exists.

[`sdpMLineIndex`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/sdpMLineIndex "sdpMLineIndex") <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
If not `null`, `sdpMLineIndex` indicates the zero-based index number of the media description (as defined in <a href="https://datatracker.ietf.org/doc/html/rfc4566" class="external">RFC 4566</a>) in the [SDP](https://developer.mozilla.org/en-US/docs/Glossary/SDP) with which the candidate is associated.

[`tcpType`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/tcpType "tcpType") <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
If `protocol` is `"tcp"`, `tcpType` represents the type of TCP candidate. Otherwise, `tcpType` is `null`.

[`type`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/type "type") <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) indicating the type of candidate as one of the strings from the [`RTCIceCandidateType`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidateType) enumerated type.

[`usernameFragment`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/usernameFragment "usernameFragment") <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) containing a randomly-generated username fragment ("ice-ufrag") which ICE uses for message integrity along with a randomly-generated password ("ice-pwd"). You can use this string to verify generations of ICE generation; each generation of the same ICE process will use the same `usernameFragment`, even across ICE restarts.

[Methods](#methods "Permalink to Methods")
------------------------------------------

[`toJSON()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/toJSON "toJSON()")  
Given the `RTCIceCandidate`'s current configuration, `toJSON()` returns a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) containing a [JSON](https://developer.mozilla.org/en-US/docs/Glossary/JSON) representation of that configuration in the form of a [`RTCIceCandidateInit`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidateInit) object.

[Examples](#examples "Permalink to Examples")
---------------------------------------------

For examples, see the article [Signaling and video calling](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Signaling_and_video_calling), which demonstrates the entire process.

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#rtcicecandidate-interface" class="external">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCIceCandidate' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/rtcicecandidate/index.html "Folder: en-us/web/api/rtcicecandidate (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FRTCIceCandidate%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Frtcicecandidate%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FRTCIceCandidate%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Frtcicecandidate%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fb38887c5d8925adbfe4c051f5e59132c7363f55a%0A*+Document+last+modified%3A+2021-05-31T16%3A07%3A26.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22RTCIceCandidate%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/contributors.txt)

Change your languageSelect your preferred language English (US)Deutsch한국어

Change language

#### Related Topics

1.  **[WebRTC API](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API)**
2.  **[`RTCIceCandidate`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate)**
3.  Constructor
    1.  [`RTCIceCandidate()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/RTCIceCandidate)
4.  Properties
    1.  [`address`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/address)
    2.  [`candidate`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/candidate)
    3.  [`component`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/component)
    4.  [`foundation`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/foundation)
    5.  [`port`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/port)
    6.  [`priority`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/priority)
    7.  [`protocol`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/protocol)
    8.  [`relatedAddress`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/relatedAddress)
    9.  [`relatedPort`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/relatedPort)
    10. [`sdpMid`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/sdpMid)
    11. [`sdpMLineIndex`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/sdpMLineIndex)
    12. [`usernameFragment`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/usernameFragment)
5.  Methods
    1.  [` toJSON()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/toJSON)
6.  Related pages for WebRTC
    1.  [`MediaDevices.getUserMedia()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getUserMedia)
    2.  [`Navigator.mediaDevices`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/mediaDevices)
    3.  [`RTCCertificate`](https://developer.mozilla.org/en-US/docs/Web/API/RTCCertificate)
    4.  [`RTCDTMFSender`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDTMFSender)
    5.  [`RTCDTMFToneChangeEvent`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDTMFToneChangeEvent)
    6.  [`RTCDataChannel`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel)
    7.  [`RTCDataChannelEvent`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannelEvent)
    8.  [`RTCDtlsTransport`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDtlsTransport)
    9.  [`RTCErrorEvent`](https://developer.mozilla.org/en-US/docs/Web/API/RTCErrorEvent)
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
