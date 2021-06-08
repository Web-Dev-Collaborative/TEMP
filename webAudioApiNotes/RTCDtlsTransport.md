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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCDtlsTransport" class="breadcrumb-current-page"><span data-property="name">RTCDtlsTransport</span></a>

Table of contents
-----------------

Table of contents

-   [Properties](#properties)
-   [Description](#description)
-   [Examples](#examples)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

RTCDtlsTransport
================

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

The **`RTCDtlsTransport`** interface provides access to information about the Datagram Transport Layer Security (**[DTLS](https://developer.mozilla.org/en-US/docs/Glossary/DTLS)**) transport over which a [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection)'s [RTP](https://developer.mozilla.org/en-US/docs/Glossary/RTP) and [RTCP](https://developer.mozilla.org/en-US/docs/Glossary/RTCP) packets are sent and received by its [`RTCRtpSender`](https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpSender) and [`RTCRtpReceiver`](https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpReceiver) objects.

A DTLS transport is also used to provide information about [SCTP](https://developer.mozilla.org/en-US/docs/Glossary/SCTP) packets transmitted and received by an connection's [data channels](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel).

Features of the DTLS transport include the addition of security to the underlying transport; the `RTCDtlsTransport` interface can be used to obtain information about the underlying transport and the security added to it by the DTLS layer.

[`iceTransport`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDtlsTransport/iceTransport) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
The read-only **`RTCDtlsTransport`** property `iceTransport` contains a reference to the underlying `RTCIceTransport`.

[`state`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDtlsTransport/state) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
`WebRTC`

[Description](#description "Permalink to Description")
------------------------------------------------------

### [Allocation of DTLS transports](#allocation_of_dtls_transports "Permalink to Allocation of DTLS transports")

`RTCDtlsTransport` objects are created when an app calls either [`setLocalDescription()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/setLocalDescription "setLocalDescription()") or [`setRemoteDescription()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/setRemoteDescription "setRemoteDescription()"). The number of DTLS transports created and how they're used depends on the bundling mode used when creating the [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection).

Whether bundling is used depends on what the other endpoint is able to negotiate. All browsers support bundling, so when both endpoints are browsers, you can rest assured that bundling will be used.

Some non-browser legacy endpoints, however, may not support bundle. To be able to negotiate with such endpoints (or to exclude them entirely), the [`RTCConfiguration`](https://developer.mozilla.org/en-US/docs/Web/API/RTCConfiguration) property [`bundlePolicy`](https://developer.mozilla.org/en-US/docs/Web/API/RTCConfiguration/bundlePolicy "bundlePolicy") may be provided when creating the connection. The `bundlePolicy` [lets you control](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection#rtcbundlepolicy_enum) how to negotiate with these legacy endpoints. The default policy is `"balanced"`, which provides a balance between performance and compatibility.

For example, to create the connection using the highest level of bundling:

    const rtcConfig = {
      bundlePolicy: "max-bundle"
    };

    const pc = new RTCPeerConnection(rtcConfig);

<a href="https://webrtcstandards.info/sdp-bundle/" class="external">Bundling</a> lets you use one `RTCDtlsTransport` to carry the data for multiple higher-level transports, such as multiple [`RTCRtpTransceiver`](https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpTransceiver)s.

#### When not using BUNDLE

When the connection is created without using BUNDLE, each RTP or RTCP component of each [`RTCRtpTransceiver`](https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpTransceiver) has its own `RTCDtlsTransport`; that is, every [`RTCRtpSender`](https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpSender) and [`RTCRtpReceiver`](https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpReceiver), has its own transport, and all [`RTCDataChannel`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel) objects share a transport dedicated to SCTP.

#### When using BUNDLE

When the connection is using BUNDLE, each `RTCDtlsTransport` object represents a group of [`RTCRtpTransceiver`](https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpTransceiver) objects. If the connection was created using `max-compat` mode, each transport is responsible for handling all of the communications for a given type of media (audio, video, or data channel). Thus, a connection that has any number of audio and video channels will always have exactly one DTLS transport for audio and one for video communications.

Because transports are established early in the negotiation process, it's likely that it won't be known until after they're created whether or not the remote peer supports bundling or not. For this reason, you'll sometimes see separate transports created at first, one for each track, then see them get bundled up once it's known that bundling is possible. If your code accesses  [`RTCRtpSender`](https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpSender)s and/or [`RTCRtpReceiver`](https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpReceiver)s directly, you may encounter situations where they're initially separate, then half or more of them get closed and the senders and receivers updated to refer to the appropriate remaining `RTCDtlsTransport` objects.

### [Data channels](#data_channels "Permalink to Data channels")

[`RTCDataChannel`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel)s use [SCTP](https://developer.mozilla.org/en-US/docs/Glossary/SCTP) to communicate. All of a peer connection's data channels share a single [`RTCSctpTransport`](https://developer.mozilla.org/en-US/docs/Web/API/RTCSctpTransport), found in the connection's [`sctp`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/sctp "sctp") property.

You can, in turn, identify the `RTCDtlsTransport` used to securely encapsulate the data channels' SCTP communications by looking at the `RTCSctpTransport` object's <span class="page-not-created">`transport`</span> property.

[Examples](#examples "Permalink to Examples")
---------------------------------------------

This example presents a function, `tallySenders()`, which iterates over an `RTCPeerConnection`'s [`RTCRtpSender`](https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpSender)s, tallying up how many of them are in various states. The function returns an object containing properties whose values indicate how many of the senders are in each state.

    let pc = new RTCPeerConnection({ bundlePolicy: "max-bundle" });

    /* ... */

    function tallySenders(pc) {
      let results = {
        transportMissing: 0,
        connectionPending: 0,
        connected: 0,
        closed: 0,
        failed: 0,
        unknown: 0
      };

      let senderList = pc.getSenders();
      senderList.forEach(sender => {
        let transport = sender.transport;

        if (!transport) {
          results.transportMissing++;
        } else {
          switch(transport.state) {
            case "new":
            case "connecting":
              results.connectionPending++;
              break;
           case "connected":
              results.connected++;
              break;
           case "closed":
              results.closed++;
              break;
           case "failed":
              results.failed++;
              break;
           default:
              results.unknown++;
              break;
          }
        }
      });
      return results;
    }

Note that in this code, the `new` and `connecting` states are being treated as a single `connectionPending` status in the returned object.

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcdtlstransport" class="external">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCDtlsTransport' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [`RTCRtpSender.transport`](https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpSender/transport) and [`RTCRtpReceiver.transport`](https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpReceiver/transport)
-   <span class="page-not-created">`RTCSctpTransport.transport`</span>

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/rtcdtlstransport/index.html "Folder: en-us/web/api/rtcdtlstransport (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FRTCDtlsTransport%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Frtcdtlstransport%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FRTCDtlsTransport%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Frtcdtlstransport%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fb38887c5d8925adbfe4c051f5e59132c7363f55a%0A*+Document+last+modified%3A+2021-05-31T16%3A07%3A26.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22RTCDtlsTransport%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/RTCDtlsTransport/contributors.txt)

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
