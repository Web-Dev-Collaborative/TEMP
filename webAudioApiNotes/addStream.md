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
4.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/addStream" class="breadcrumb-current-page"><span data-property="name">RTCPeerConnection.addStream()</span></a>

Table of contents
-----------------

Table of contents

-   [Syntax](#syntax)
-   [Example](#example)
-   [Migrating to addTrack()](#migrating_to_addtrack())
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

RTCPeerConnection.addStream()
=============================

#### Deprecated

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The *obsolete* [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection) method `addStream()` adds a [`MediaStream`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream) as a local source of audio or video. Instead of using this obsolete method, you should instead use [`addTrack()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/addTrack "addTrack()") once for each track you wish to send to the remote peer.

If the [`signalingState`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/signalingState "signalingState") is set to `closed`, an `InvalidStateError` is raised. If the [`signalingState`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/signalingState "signalingState") is set to `stable`, the event `negotiationneeded` is sent on the [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection) to indicate that [ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE) negotiation must be repeated to consider the new stream.

[Syntax](#syntax "Permalink to Syntax")
---------------------------------------

    rtcPeerConnection.addStream(mediaStream);

### [Parameters](#parameters "Permalink to Parameters")

`mediaStream`  
A [`MediaStream`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream) object indicating the stream to add to the WebRTC peer connection.

### [Return value](#return_value "Permalink to Return value")

None.

[Example](#example "Permalink to Example")
------------------------------------------

This simple example adds the audio and video stream coming from the user's camera to the connection.

    navigator.mediaDevices.getUserMedia({video:true, audio:true}, function(stream) {
      var pc = new RTCPeerConnection();
      pc.addStream(stream);
    });

[Migrating to addTrack()](#migrating_to_addtrack() "Permalink to Migrating to addTrack()")
------------------------------------------------------------------------------------------

[Compatibility allowing](#browser_compatibility), you should update your code to instead use the [`addTrack()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/addTrack "addTrack()") method:

    navigator.getUserMedia({video:true, audio:true}, function(stream) {
      var pc = new RTCPeerConnection();
      stream.getTracks().forEach(function(track) {
        pc.addTrack(track, stream);
      });
    });

The newer [`addTrack()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/addTrack "addTrack()") API avoids confusion over whether later changes to the track-makeup of a stream affects a peer connection (they do not).

The exception is in Chrome, where `addStream()` *does* make the peer connection sensitive to later stream changes (though such changes do not fire the `negotiationneeded` event). If you are relying on the Chrome behavior, note that other browsers do not have it. You can write web compatible code using feature detection instead:

    // Add a track to a stream and the peer connection said stream was added to:

    stream.addTrack(track);
    if (pc.addTrack) {
      pc.addTrack(track, stream);
    } else {
      // If you have code listening for negotiationneeded events:
      setTimeout(() => pc.dispatchEvent(new Event('negotiationneeded')));
    }

    // Remove a track from a stream and the peer connection said stream was added to:

    stream.removeTrack(track);
    if (pc.removeTrack) {
      pc.removeTrack(pc.getSenders().find(sender => sender.track == track));
    } else {
      // If you have code listening for negotiationneeded events:
      setTimeout(() => pc.dispatchEvent(new Event('negotiationneeded')));
    }

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#legacy-interface-extensions" class="external">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCPeerConnection.addStream()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [WebRTC](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/rtcpeerconnection/addstream/index.html "Folder: en-us/web/api/rtcpeerconnection/addstream (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FRTCPeerConnection%2FaddStream%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Frtcpeerconnection%2Faddstream%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FRTCPeerConnection%2FaddStream%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Frtcpeerconnection%2Faddstream%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fb38887c5d8925adbfe4c051f5e59132c7363f55a%0A*+Document+last+modified%3A+2021-05-31T16%3A07%3A26.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22RTCPeerConnection.addStream%28%29%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/addStream/contributors.txt)

#### Related Topics

1.  **[WebRTC API](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API)**
2.  **[`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection)**
3.  Constructor
    1.  [`RTCPeerConnection()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/RTCPeerConnection)
4.  Properties
    1.  [`canTrickleIceCandidates`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/canTrickleIceCandidates)
    2.  [`connectionState`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/connectionState)
    3.  [`currentLocalDescription`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/currentLocalDescription)
    4.  [`currentRemoteDescription`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/currentRemoteDescription)
    5.  [`iceConnectionState`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/iceConnectionState)
    6.  [`iceGatheringState`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/iceGatheringState)
    7.  [`localDescription`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/localDescription)
    8.  [`onaddstream`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/onaddstream)
    9.  [`onconnectionstatechange`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/onconnectionstatechange)
    10. [`ondatachannel`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/ondatachannel)
    11. [`onicecandidate`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/onicecandidate)
    12. [`oniceconnectionstatechange`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/oniceconnectionstatechange)
    13. [`onicegatheringstatechange`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/onicegatheringstatechange)
    14. [`onidentityresult`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/onidentityresult)
    15. [`onidpassertionerror`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/onidpassertionerror)
    16. [`onidpvalidationerror`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/onidpvalidationerror)
    17. [`onnegotiationneeded`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/onnegotiationneeded)
    18. [`onpeeridentity`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/onpeeridentity)
    19. [`onremovestream`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/onremovestream)
    20. [`onsignalingstatechange`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/onsignalingstatechange)
    21. [`ontrack`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/ontrack)
    22. [`peerIdentity`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/peerIdentity)
    23. [`pendingLocalDescription`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/pendingLocalDescription)
    24. [`pendingRemoteDescription`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/pendingRemoteDescription)
    25. [`remoteDescription`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/remoteDescription)
    26. [`sctp`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/sctp)
    27. [`signalingState`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/signalingState)
5.  Methods
    1.  [`addIceCandidate()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/addIceCandidate)
    2.  *`addStream()`*
    3.  [`addTrack()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/addTrack)
    4.  [`close()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/close)
    5.  [`createAnswer()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/createAnswer)
    6.  [`createDataChannel()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/createDataChannel)
    7.  [`createOffer()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/createOffer)
    8.  [`generateCertificate() static function`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/generateCertificate)
    9.  [`getConfiguration()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/getConfiguration)
    10. [`getIdentityAssertion()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/getIdentityAssertion)
    11. [`getReceivers()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/getReceivers)
    12. [`getSenders()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/getSenders)
    13. [`getStats()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/getStats)
    14. [`getStreamById()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/getStreamById)
    15. [`getTransceivers()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/getTransceivers)
    16. [`removeStream()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/removeStream)
    17. [`removeTrack()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/removeTrack)
    18. [`restartIce()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/restartIce)
    19. [`setConfiguration()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/setConfiguration)
    20. [`setIdentityProvider()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/setIdentityProvider)
    21. [`setLocalDescription()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/setLocalDescription)
    22. [`setRemoteDescription()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/setRemoteDescription)
6.  Events
    1.  [`addstream`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/addstream_event)
    2.  [`icecandidateerror`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/icecandidateerror_event)
    3.  [`identityresult`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/identityresult_event)
    4.  [`negotiationneeded`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/negotiationneeded_event)
    5.  [`removestream`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/removestream_event)
    6.  [`signalingstatechange`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/signalingstatechange_event)
7.  Inheritance:
    1.  [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)
8.  Related pages for WebRTC
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