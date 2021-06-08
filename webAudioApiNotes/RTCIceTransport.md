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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport" class="breadcrumb-current-page"><span data-property="name">RTCIceTransport</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Properties](#properties)
-   [Methods](#methods)
-   [Events](#events)
-   [Examples](#examples)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)

RTCIceTransport
===============

<span class="seoSummary">The `RTCIceTransport` interface provides access to information about the [ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE) transport layer over which the data is being sent and received.</span> This is particularly useful if you need to access state information about the connection.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

*The `RTCIceTransport` interface inherits properties from its parent, [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget). It also offers the following properties:*

[`component`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/component "component") <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
The ICE component being used by the transport. The value is one of the strings from the [`RTCIceTransport`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport) enumerated type: `"RTP"` or `"RTSP"`.

[`gatheringState`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/gatheringState "gatheringState") <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) indicating which gathering state the ICE agent is currently in. The value is one of those included in the [`RTCIceGathererState`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceGathererState) enumerated type: `"new"`, `"gathering"`, or `"complete"`.

[`role`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/role "role") <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) whose value is one of the members of the [`RTCIceRole`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceRole) enumerated type: `"controlling"` or `"controlled"`; this indicates whether the ICE agent is the one that makes the final decision as to the candidate pair to use or not.

[`state`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/state "state") <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) indicating what the current state of the ICE agent is. The value of `state` can be used to determine whether the ICE agent has made an initial connection using a viable candidate pair (`"connected"`), made its final selection of candidate pairs (`"completed"`), or in an error state (`"failed"`), among other states. See the [`RTCIceTransportState`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransportState) enumerated type for a complete list of states.

[Methods](#methods "Permalink to Methods")
------------------------------------------

*Also includes methods from [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget), the parent interface.*

[`getLocalCandidates()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/getLocalCandidates "getLocalCandidates()")  
Returns an array of [`RTCIceCandidate`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate) objects, each describing one of the ICE candidates that have been gathered so far for the local device. These are the same candidates which have already been sent to the remote peer by sending an `icecandidate` event to the [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection) for transmission.

[`getLocalParameters()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/getLocalParameters "getLocalParameters()")  
Returns a [`RTCIceParameters`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceParameters) object describing the ICE parameters established by a call to the [`RTCPeerConnection.setLocalDescription()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/setLocalDescription) method. Returns `null` if parameters have not yet been received.

[`getRemoteCandidates()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/getRemoteCandidates "getRemoteCandidates()")  
Returns an array of [`RTCIceCandidate`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate) objects, one for each of the remote device's ICE candidates that have been received by the local end of the [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection) and delivered to ICE by calling [`addIceCandidate()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/addIceCandidate "addIceCandidate()").

[`getRemoteParameters()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/getRemoteParameters "getRemoteParameters()")  
Returns a [`RTCIceParameters`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceParameters) object containing the ICE parameters for the remote device, as set by a call to [`RTCPeerConnection.setRemoteDescription()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/setRemoteDescription). If `setRemoteDescription()` hasn't been called yet, the return value is `null`.

[`getSelectedCandidatePair()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/getSelectedCandidatePair "getSelectedCandidatePair()")  
Returns a [`RTCIceCandidatePair`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePair) object that identifies the two candidates—one for each end of the connection—that have been selected so far. It's possible that a better pair will be found and selected later; if you need to keep up with this, watch for the `selectedcandidatepairchange` event. If no candidate pair has been selected yet, the return value is `null`.

[Events](#events "Permalink to Events")
---------------------------------------

Listen to these events using [`addEventListener()`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener "addEventListener()") or by assigning an event listener to the `oneventname` property of this interface.

[`gatheringstatechange`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/gatheringstatechange_event "gatheringstatechange")  
Sent to the [`RTCIceTransport`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport) object to indicate that the value of the [`gatheringState`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/gatheringState "gatheringState") property has changed, indicating a change in this transport's ICE candidate negotiation process.  
Also available through the [`ongatheringstatechange`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/ongatheringstatechange "ongatheringstatechange") event handler property.

[`selectedcandidatepairchange`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/selectedcandidatepairchange_event "selectedcandidatepairchange")  
Sent to the `RTCIceTransport` when a new, better pair of candidates has been selected to describe the connectivity between the two peers. This occurs during negotiation or renegotiation, including after an ICE restart, which reuses the existing `RTCIceTransport` objects. The current candidate pair can be obtained using [`getSelectedCandidatePair()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/getSelectedCandidatePair "getSelectedCandidatePair()").  
Also available using the [`onselectedcandidatepairchange`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/onselectedcandidatepairchange "onselectedcandidatepairchange") event handler property.

[`statechange`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/statechange_event "statechange")  
Sent to the `RTCIceTransport` instance when the value of the [`state`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/state "state") property has changed, indicating that the ICE gathering process has changed state.  
Also available through the [`onstatechange`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/onstatechange "onstatechange") event handler property.

[Examples](#examples "Permalink to Examples")
---------------------------------------------

tbd

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcicetransport" class="external">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCIceTransport' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/rtcicetransport/index.html "Folder: en-us/web/api/rtcicetransport (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FRTCIceTransport%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Frtcicetransport%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FRTCIceTransport%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Frtcicetransport%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fb38887c5d8925adbfe4c051f5e59132c7363f55a%0A*+Document+last+modified%3A+2021-05-31T16%3A07%3A26.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22RTCIceTransport%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/contributors.txt)

Change your languageSelect your preferred language English (US)Português (do Brasil)

Change language

#### Related Topics

1.  **[WebRTC API](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API)**
2.  **[`RTCIceTransport`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport)**
3.  Properties
    1.  [`component`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/component)
    2.  [`gatheringState`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/gatheringState)
    3.  [`getRemoteCandidates()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/getRemoteCandidates)
    4.  [`ongatheringstatechange`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/ongatheringstatechange)
    5.  [`onselectedcandidatepairchange`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/onselectedcandidatepairchange)
    6.  [`onstatechange`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/onstatechange)
    7.  [`role`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/role)
    8.  [`state`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/state)
4.  Methods
    1.  [`getLocalCandidates()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/getLocalCandidates)
    2.  [`getLocalParameters()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/getLocalParameters)
    3.  [`getSelectedCandidatePair()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/getSelectedCandidatePair)
5.  Related pages for WebRTC
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
