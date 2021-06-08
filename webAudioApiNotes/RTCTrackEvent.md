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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCTrackEvent" class="breadcrumb-current-page"><span data-property="name">RTCTrackEvent</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Constructor](#constructor)
-   [Properties](#properties)
-   [Track event types](#track_event_types)
-   [Example](#example)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)

RTCTrackEvent
=============

<span class="seoSummary">The [WebRTC API](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API) interface `RTCTrackEvent` represents the `track` event, which is sent when a new [`MediaStreamTrack`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack) is added to an [`RTCRtpReceiver`](https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpReceiver) which is part of the [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection).</span> The target is the `RTCPeerConnection` object to which the track is being added.

This event is sent by the WebRTC layer to the web site or application, so you will not typically need to instantiate an `RTCTrackEvent` yourself.

[Constructor](#constructor "Permalink to Constructor")
------------------------------------------------------

[`RTCTrackEvent()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCTrackEvent/RTCTrackEvent "RTCTrackEvent()")  
Creates and returns a new `RTCTrackEvent` object, initialized with properties taken from the specified [`RTCTrackEventInit`](https://developer.mozilla.org/en-US/docs/Web/API/RTCTrackEventInit) dictionary. You will probably not need to create new track events yourself, since they're typically created by the WebRTC infrastructure and sent to the connection's [`ontrack`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/ontrack "ontrack") event handler.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

*Since `RTCTrackEvent` is based on [`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event), its properties are also available.*

[`receiver`](https://developer.mozilla.org/en-US/docs/Web/API/RTCTrackEvent/receiver "receiver") <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
The [`RTCRtpReceiver`](https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpReceiver) used by the track that's been added to the `RTCPeerConnection`.

[`streams`](https://developer.mozilla.org/en-US/docs/Web/API/RTCTrackEvent/streams "streams") <span class="badge inline readonly" title="This value may not be changed.">Read only </span> <span class="badge inline optional">Optional</span>  
An array of [`MediaStream`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream) objects, each representing one of the media streams to which the added [`track`](https://developer.mozilla.org/en-US/docs/Web/API/RTCTrackEvent/track "track") belongs. By default, the array is empty, indicating a streamless track.

[`track`](https://developer.mozilla.org/en-US/docs/Web/API/RTCTrackEvent/track "track") <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
The [`MediaStreamTrack`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack) which has been added to the connection.

[`transceiver`](https://developer.mozilla.org/en-US/docs/Web/API/RTCTrackEvent/transceiver "transceiver") <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
The [`RTCRtpTransceiver`](https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpTransceiver) being used by the new track.

[Track event types](#track_event_types "Permalink to Track event types")
------------------------------------------------------------------------

There is only one type of track event.

### [`track`](#track "Permalink to track")

The [`track`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/track_event "track") event is sent to the [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection) when a new track has been added to the connection. By the time the `track` event is delivered to the `RTCPeerConnection`'s [`ontrack`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/ontrack "ontrack") handler, the new media has completed its negotiation for a specific [`RTCRtpReceiver`](https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpReceiver) (which is specified by the event's [`receiver`](https://developer.mozilla.org/en-US/docs/Web/API/RTCTrackEvent/receiver "receiver") property).

In addition, the [`MediaStreamTrack`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack) specified by the receiver's [`track`](https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpReceiver/track "track") is the same one specified by the event's [`track`](https://developer.mozilla.org/en-US/docs/Web/API/RTCTrackEvent/track "track"), and the track has been added to any associated remote [`MediaStream`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream) objects.

You can add a `track` event listener to be notified when the new track is available so that you can, for example, attach its media to a [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element, using either [`RTCPeerConnection.addEventListener()`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener "RTCPeerConnection.addEventListener()") or the `ontrack` event handler property.

**Note:** It may be helpful to keep in mind that you receive the `track` event when a new inbound track has been added to your connection, and you call [`addTrack()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/addTrack "addTrack()") to add a track to the far end of the connection, thereby triggering a `track` event on the remote peer.

[Example](#example "Permalink to Example")
------------------------------------------

This simple example creates an event listener for the [`track`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/track_event "track") event which sets the [`srcObject`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/srcObject "srcObject") of the [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element with the ID `videobox` to the first stream in the list passed in the event's [`streams`](https://developer.mozilla.org/en-US/docs/Web/API/RTCTrackEvent/streams "streams") array.

    peerConnection.addEventListener("track", e => {
      let videoElement = document.getElementById("videobox");
      videoElement.srcObject = e.streams[0];
    }, false);

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtctrackevent" class="external">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCTrackEvent' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/rtctrackevent/index.html "Folder: en-us/web/api/rtctrackevent (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FRTCTrackEvent%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Frtctrackevent%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FRTCTrackEvent%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Frtctrackevent%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fb38887c5d8925adbfe4c051f5e59132c7363f55a%0A*+Document+last+modified%3A+2021-05-31T16%3A07%3A26.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22RTCTrackEvent%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/RTCTrackEvent/contributors.txt)

Change your languageSelect your preferred language English (US)中文 (简体)

Change language

#### Related Topics

1.  **[WebRTC API](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API)**
2.  **[`RTCTrackEvent`](https://developer.mozilla.org/en-US/docs/Web/API/RTCTrackEvent)**
3.  Constructor
    1.  [`RTCTrackEvent()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCTrackEvent/RTCTrackEvent)
4.  Properties
    1.  [`receiver`](https://developer.mozilla.org/en-US/docs/Web/API/RTCTrackEvent/receiver)
    2.  [`streams`](https://developer.mozilla.org/en-US/docs/Web/API/RTCTrackEvent/streams)
    3.  [`track`](https://developer.mozilla.org/en-US/docs/Web/API/RTCTrackEvent/track)
    4.  [`transceiver`](https://developer.mozilla.org/en-US/docs/Web/API/RTCTrackEvent/transceiver)
5.  Inheritance:
    1.  [`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event)
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
