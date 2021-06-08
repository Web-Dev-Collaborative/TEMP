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
4.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/setRemoteDescription" class="breadcrumb-current-page"><span data-property="name">RTCPeerConnection.setRemoteDescription()</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Syntax](#syntax)
-   [Usage notes](#usage_notes)
-   [Deprecated syntax](#deprecated_syntax)
-   [Example](#example)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

RTCPeerConnection.setRemoteDescription()
========================================

<span class="seoSummary">The [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection) method `setRemoteDescription()` sets the specified session description as the remote peer's current offer or answer. The description specifies the properties of the remote end of the connection, including the media format.</span> The method takes a single parameter—the session description—and it returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which is fulfilled once the description has been changed, asynchronously.

This is typically called after receiving an offer or answer from another peer over the signaling server. Keep in mind that if `setRemoteDescription()` is called while a connection is already in place, it means renegotiation is underway (possibly to adapt to changing network conditions).

Because descriptions will be exchanged until the two peers agree on a configuration, the description submitted by calling `setRemoteDescription()` does not immediately take effect. Instead, the current connection configuration remains in place until negotiation is complete. Only then does the agreed-upon configuration take effect.

[Syntax](#syntax "Permalink to Syntax")
---------------------------------------

    aPromise = rtcPeerConnection.setRemoteDescription(sessionDescription);

### [Parameters](#parameters "Permalink to Parameters")

`sessionDescription`  
An <span class="page-not-created">`RTCSessionDescriptionInit`</span> or [`RTCSessionDescription`](https://developer.mozilla.org/en-US/docs/Web/API/RTCSessionDescription) which specifies the remote peer's current offer or answer. This value is an offer or answer received from the remote peer through your implementation of 

The `sessionDescription` parameter is technically of type `RTCSessionDescriptionInit`, but because [`RTCSessionDescription`](https://developer.mozilla.org/en-US/docs/Web/API/RTCSessionDescription) serializes to be indistinguishable from `RTCSessionDescriptionInit`, you can also pass in an `RTCSessionDescription`. This lets you simplify code such as the following:

    myPeerConnection.setRemoteDescription(new RTCSessionDescription(description))
    .then(function () {
      return createMyStream();
    })

to be:

    myPeerConnection.setRemoteDescription(description)
    .then(function () {
      return createMyStream();
    })

Using `async`/`await` syntax, you can further simplify this to:

    await myPeerConnection.setRemoteDescription(description);
    createMyStream();

Since it's unnecessary, the [`RTCSessionDescription()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCSessionDescription/RTCSessionDescription "RTCSessionDescription()") constructor is deprecated.

### [Return value](#return_value "Permalink to Return value")

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which is fulfilled once the value of the connection's [`remoteDescription`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/remoteDescription "remoteDescription") is successfully changed or rejected if the change cannot be applied (for example, if the specified description is incompatible with one or both of the peers on the connection). The promise fulfillment handler receives no input parameters.

**Note:** The process of changing descriptions actually involves intermediary steps handled by the WebRTC layer to ensure that an active connection can be changed without losing the connection if the change does not succeed. See [Pending and current descriptions](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Connectivity#pending_and%0A%20%20%20%20%20%20%20%20current_descriptions) in [WebRTC connectivity](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Connectivity) for more details on this process.

### [Exceptions](#exceptions "Permalink to Exceptions")

The following exceptions are reported to the rejection handler for the promise returned by `setRemoteDescription()`:

`InvalidAccessError`  
The content of the description is invalid.

`InvalidStateError`  
The [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection) is closed, or it's in a state which isn't compatible with the specified description's [`type`](https://developer.mozilla.org/en-US/docs/Web/API/RTCSessionDescription/type "type"). For example, if the `type` is `rollback` and the signaling state is one of `stable`, `have-local-pranswer`, or `have-remote-pranswer`, this exception is thrown, because you can't roll back a connection that's either fully established or is in the final stage of becoming connected.

`OperationError`  
Any errors that occur which don't match the others specifeid here are reported as `OperationError`. This includes identity validation errors.

`RTCError`  
An `RTCError` with the [`errorDetail`](https://developer.mozilla.org/en-US/docs/Web/API/RTCError/errorDetail "errorDetail") set to `sdp-syntax-error` is reported if the [SDP](https://developer.mozilla.org/en-US/docs/Glossary/SDP) specified by [`RTCSessionDescription.sdp`](https://developer.mozilla.org/en-US/docs/Web/API/RTCSessionDescription/sdp). The error object's [`sdpLineNumber`](https://developer.mozilla.org/en-US/docs/Web/API/RTCError/sdpLineNumber "sdpLineNumber") property indicates the line number within the SDP on which the syntax error was detected.

`TypeError`  
The specified `RTCSessionDescriptionInit` or `RTCSessionDescription` object is missing the [`type`](https://developer.mozilla.org/en-US/docs/Web/API/RTCSessionDescription/type "type") property, or no description parameter was provided at all.

[Usage notes](#usage_notes "Permalink to Usage notes")
------------------------------------------------------

When you call `setRemoteDescription()`, the ICE agent checks to make sure the [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection) is in either the `stable` or `have-remote-offer` [`signalingState`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/signalingState "signalingState"). These states indicate that either an existing connection is being renegotiated or that an offer previously specified by an earlier call to `setRemoteDescription()` is to be replaced with the new offer. In either of those two cases, we're at the beginning of the negotiation process, and the offer is set as the remote description.

On the other hand, if we're in the middle of an ongoing negotiation and an offer is passed into `setRemoteDescription()`, the ICE agent automatically begins an ICE rollback in order to return the connection to a stable signaling state, then, once the rollback is completed, sets the remote description to the specified offer. This begins a new negotiation session, with the newly-established offer as the starting point.

Upon starting the new negotiation with the newly-established offer, the local peer is now the callee, even if it was previously the caller. This happens instead of throwing an exception, thereby reducing the number of potential errors which might occur, and simplifies the processing you need to do when you receive an offer, by eliminating the need to handle the offer/answer process differently depending on whether the local peer is the caller or callee.

**Note:** Earlier implementations of WebRTC would throw an exception if an offer was set outside a `stable` or `have-remote-offer` state.

[Deprecated syntax](#deprecated_syntax "Permalink to Deprecated syntax")
------------------------------------------------------------------------

In older code and documentation, you may see a callback-based version of this function used. This has been deprecated and its use is *strongly* discouraged. You should update any existing code to use the [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)-based version of `setRemoteDescription()` instead. The parameters for the older form of `setRemoteDescription()` are described below, to aid in updating existing code.

    pc.setRemoteDescription(sessionDescription, successCallback, errorCallback);

### [Parameters](#parameters_2 "Permalink to Parameters")

`successCallback`   
A JavaScript [`Function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function) which accepts no input parameters to be called once the description has been successfully set. At that time, the offer can be sent to a remote peer via the signaling server.

`errorCallback`   
A function matching the signautre `RTCPeerConnectionErrorCallback` which gets called if the description can't be set. It is passed a single [`DOMException`](https://developer.mozilla.org/en-US/docs/Web/API/DOMException) object explaining why the request failed.

This deprecated form of the method returns instantaneously without waiting for the actual setting to be done: in case of success, the `successCallback` will be called; in case of failure, the `errorCallback` will be called.

### [Exceptions](#exceptions_2 "Permalink to Exceptions")

When using the deprecated callback-based version of `setRemoteDescription()`, the following exceptions may occur:

`InvalidStateError`   
The connection's [`signalingState`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/signalingState "signalingState") is `"closed"`, indicating that the connection is not currently open, so negotiation cannot take place.

`InvalidSessionDescriptionError`   
The [`RTCSessionDescription`](https://developer.mozilla.org/en-US/docs/Web/API/RTCSessionDescription) specified by the `sessionDescription` parameter is invalid.

[Example](#example "Permalink to Example")
------------------------------------------

Here we see a function which handles an offer received from the remote peer. This code is derived from the example and tutorial in the article [Signaling and video calling](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Signaling_and_video_calling); take a look at that for more details and a more in-depth explanation of what's going on.

    function handleOffer(msg) {
      createMyPeerConnection();

      myPeerConnection.setRemoteDescription(msg.description).then(function () {
        return navigator.mediaDevices.getUserMedia(mediaConstraints);
      })
      .then(function(stream) {
        document.getElementById("local_video").srcObject = stream;
        return myPeerConnection.addStream(stream);
      })
      .then(function() {
        return myPeerConnection.createAnswer();
      })
      .then(function(answer) {
        return myPeerConnection.setLocalDescription(answer);
      })
      .then(function() {
        // Send the answer to the remote peer using the signaling server
      })
      .catch(handleGetUserMediaError);
    }

After creating our [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection) and saving it as `myPeerConnection`, we pass the description included in the received offer message, `msg`, directly into `setRemoteDescription()` to tell the user agent's WebRTC layer what configuration the caller has proposed using. When our promise fulfillment handler is called, indicating that this has been done, we create a stream, add it to the connection, then create an SDP answer and call [`setLocalDescription()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/setLocalDescription "setLocalDescription()") to set that as the configuration at our end of the call before forwarding that answer to the caller.

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-peerconnection-setremotedescription" class="external">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCPeerConnection.setRemoteDescription()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [WebRTC](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API)
-   [`RTCPeerConnection.remoteDescription`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/remoteDescription), [`RTCPeerConnection.pendingRemoteDescription`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/pendingRemoteDescription), [`RTCPeerConnection.currentRemoteDescription`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/currentRemoteDescription)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/rtcpeerconnection/setremotedescription/index.html "Folder: en-us/web/api/rtcpeerconnection/setremotedescription (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FRTCPeerConnection%2FsetRemoteDescription%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Frtcpeerconnection%2Fsetremotedescription%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FRTCPeerConnection%2FsetRemoteDescription%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Frtcpeerconnection%2Fsetremotedescription%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fb38887c5d8925adbfe4c051f5e59132c7363f55a%0A*+Document+last+modified%3A+2021-05-31T16%3A07%3A26.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22RTCPeerConnection.setRemoteDescription%28%29%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/setRemoteDescription/contributors.txt)

Change your languageSelect your preferred language English (US)中文 (简体)

Change language

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
    2.  [`addStream()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/addStream)
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
    22. *`setRemoteDescription()`*
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
