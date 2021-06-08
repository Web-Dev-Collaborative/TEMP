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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCStatsReport" class="breadcrumb-current-page"><span data-property="name">RTCStatsReport</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [The statistics objects](#the_statistics_objects)
-   [Using RTCStatsReport](#using_rtcstatsreport)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

RTCStatsReport
==============

#### Draft

This page is not complete.

*This page is currently incomplete and under active construction. Please be aware that it's not going to answer all of your questions just yet.*

<span class="seoSummary">The `RTCStatsReport` interface provides a statistics report obtained by calling one of the [`RTCPeerConnection.getStats()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/getStats), [`RTCRtpReceiver.getStats()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpReceiver/getStats), and [`RTCRtpSender.getStats()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpSender/getStats) methods.</span> This statistics report contains a mapping of statistic category string names to objects containing the corresponding statistics data.

Calling `getStats()` on an [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection) lets you specify whether you wish to obtain statistics for outbound, inbound, or all streams on the connection. The [`RTCRtpReceiver`](https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpReceiver) and [`RTCRtpSender`](https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpSender) versions of `getStats()` specifically only return statistics available to the incoming or outgoing stream on which you call them.

[The statistics objects](#the_statistics_objects "Permalink to The statistics objects")
---------------------------------------------------------------------------------------

For each category of statistic information, there is a dictionary whose properties provide the relevant information.

### [Properties common to all statistic categories](#properties_common_to_all_statistic_categories "Permalink to Properties common to all statistic categories")

All WebRTC statistics objects are fundamentally based on the [`RTCStats`](https://developer.mozilla.org/en-US/docs/Web/API/RTCStats) dictionary, which provides the most fundamental information: the timestamp, the statistic type string, and an ID uniquely identifying the source of the data:

[`id`](https://developer.mozilla.org/en-US/docs/Web/API/RTCStats/id "id")  
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) which uniquely identifies the object which was inspected to produce this object based on `RTCStats`.

[`timestamp`](https://developer.mozilla.org/en-US/docs/Web/API/RTCStats/timestamp "timestamp")  
A [`DOMHighResTimeStamp`](https://developer.mozilla.org/en-US/docs/Web/API/DOMHighResTimeStamp) object indicating the time at which the sample was taken for this statistics object.

[`type`](https://developer.mozilla.org/en-US/docs/Web/API/RTCStats/type "type")  
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) indicating the type of statistics the object contains, taken from the enum type [`RTCStatsType`](https://developer.mozilla.org/en-US/docs/Web/API/RTCStatsType).

### [The statistic categories](#the_statistic_categories "Permalink to The statistic categories")

The [`type`](https://developer.mozilla.org/en-US/docs/Web/API/RTCStats/type "type") gives the name of the statistic category represented by the object, and is how you locate the specific type of data you need. The statistic category names are members of the enumerated type [`RTCStatsType`](https://developer.mozilla.org/en-US/docs/Web/API/RTCStatsType), as follows:

`candidate-pair`  
An [`RTCIceCandidatePairStats`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePairStats) object providing statistics related to an [`RTCIceTransport`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport). Candidate pairs other than the currently active pair for the transport are deleted when the [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection) changes its [`RTCPeerConnection.iceGatheringState`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/iceGatheringState) to `new` during an [ICE restart](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Session_lifetime#ice_restart). The active candidate pair is deleted after the transport switches to another candidate pair; this change cannot be detected otherwise.

`certificate`  
An <span class="page-not-created">`RTCCertificateStats`</span> object providing statistics related to a certificate being used by an [`RTCIceTransport`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport).

`codec`  
An <span class="page-not-created">`RTCCodecStats`</span> object containing statistics about a codec currently being used by [RTP](https://developer.mozilla.org/en-US/docs/Glossary/RTP) streams to send or receive data for the [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection).

`csrc`  
An <span class="page-not-created">`RTCContributingSourceStats`</span> object which contains statistics related to a contributing source (CSRC) that contributed to an inbound RTP stream.

`data-channel`  
An <span class="page-not-created">`RTCDataChannelStats`</span> object which contains statistics about each [`RTCDataChannel`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel) on the connection.

`inbound-rtp`  
An [`RTCInboundRtpStreamStats`](https://developer.mozilla.org/en-US/docs/Web/API/RTCInboundRtpStreamStats) object providing statistics about *inbound* data being received from remote peers. Since this only provides statistics related to inbound data, without considering the local peer's state, any values that require knowledge of both, such as round-trip time, is not included. This report isn't available if there are no connected peers.

`local-candidate`  
An [`RTCIceCandidateStats`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidateStats) object giving statistics about an ICE local candidate; these candidates are found in the output from [`RTCIceTransport.getLocalCandidates()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/getLocalCandidates).

`outbound-rtp`  
The report is an [`RTCOutboundRtpStreamStats`](https://developer.mozilla.org/en-US/docs/Web/API/RTCOutboundRtpStreamStats) object providing statistics based on the local peer's *outgoing* data being sent to its peers. This information considers only the outbound RTP stream, so any data which requires information about the state of the remote peers (such as round-trip time) is unavailable, since those values can't be computed without knowing about the other peers' states.

`peer-connection`  
A <span class="page-not-created">`RTCPeerConnectionStats`</span> object provides statistics related to the overall peer connection's [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection).

`receiver`  
Provides statistics about a specific [`RTCRtpReceiver`](https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpReceiver). The statistics object is an <span class="page-not-created">`RTCAudioReceiverStats`</span> object if <span class="page-not-created">`kind`</span> is `audio`; if `kind` is `video`, the object is an <span class="page-not-created">`RTCVideoReceiverStats`</span> object.

`remote-candidate`  
The report is an [`RTCIceCandidateStats`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidateStats) object containing statistics about the remote candidate's [`RTCIceTransport`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport). This may include information such as the type of network, the protocol, the URL, the type of relay being used, and so forth.

`remote-inbound-rtp`  
The report is an <span class="page-not-created">`RTCRemoteInboundRtpStreamStats`</span> object providing statistics about your outbound RTP data stream, but from the perspective of the remote peer. That is, this information is about your `outbound-rtp` stream, but as seen by the remote device that's handling the stream. You can use this information to do things like determine how well the remote peer is receiving data.

`remote-outbound-rtp`  
The report is an [`RTCRemoteOutboundRtpStreamStats`](https://developer.mozilla.org/en-US/docs/Web/API/RTCRemoteOutboundRtpStreamStats) object that contains statistics about your inbound RTP (`inbound-rtp`) stream, but from the perspective of the remote peer.

`sender`  
An object containing statistics about the [`RTCRtpSender`](https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpSender) for a stream on the [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection). If <span class="page-not-created">`kind`</span> is `"audio"`, this object is of type <span class="page-not-created">`RTCAudioSenderStats`</span>; if `kind` is `"video"`, this is an <span class="page-not-created">`RTCVideoSenderStats`</span> object.

`stream`  
An object of type <span class="page-not-created">`RTCMediaStreamStats`</span>, providing statistics and information about a [`MediaStream`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream) which is part of the [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection).

`track`  
The object is one of the types based on <span class="page-not-created">`RTCMediaHandlerStats`</span>: for audio tracks, the type is <span class="page-not-created">`RTCSenderAudioTrackAttachmentStats`</span> and for video tracks, the type is <span class="page-not-created">`RTCSenderVideoTrackAttachmentStats`</span>. The data within provides statistics related to a particular [`MediaStreamTrack`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack)'s attachment to an [`RTCRtpSender`](https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpSender); also included are the media level metrics that go along with the track.

`transport`  
An object that contains statistics related to a transport for an `RTCPeerConnection`. The object is of type <span class="page-not-created">`RTCTransportStats`</span>.

[Using RTCStatsReport](#using_rtcstatsreport "Permalink to Using RTCStatsReport")
---------------------------------------------------------------------------------

*... coming soon-ish ...*

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#rtcstatsreport-object" class="external">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCStatsReport' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [WebRTC API](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API)
-   [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection)
-   [`RTCPeerConnection.getStats()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/getStats), [`RTCRtpReceiver.getStats()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpReceiver/getStats), and [`RTCRtpSender.getStats()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpSender/getStats)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/rtcstatsreport/index.html "Folder: en-us/web/api/rtcstatsreport (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FRTCStatsReport%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Frtcstatsreport%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FRTCStatsReport%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Frtcstatsreport%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fb38887c5d8925adbfe4c051f5e59132c7363f55a%0A*+Document+last+modified%3A+2021-05-31T16%3A07%3A26.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22RTCStatsReport%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/RTCStatsReport/contributors.txt)

Change your languageSelect your preferred language English (US)中文 (简体)

Change language

#### Related Topics

1.  **[WebRTC API](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API)**
2.  **[`RTCStatsReport`](https://developer.mozilla.org/en-US/docs/Web/API/RTCStatsReport)**
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
