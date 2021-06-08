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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_Statistics_API" class="breadcrumb-current-page"><span data-property="name">WebRTC Statistics API</span></a>

Table of contents
-----------------

Table of contents

-   [Collecting statistics](#collecting_statistics)
-   [Commonly used statistics](#commonly_used_statistics)
-   [Reference](#reference)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)

WebRTC Statistics API
=====================

#### Draft

This page is not complete.

The WebRTC API has a vast array of statistics available, covering the entire breadth of the WebRTC connectivity system, from sender to receiver and peer to peer.

[Collecting statistics](#collecting_statistics "Permalink to Collecting statistics")
------------------------------------------------------------------------------------

You can collect statistics at various levels throughout the WebRTC hierarchy of objects. Most broadly, you can call [`getStats()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/getStats "getStats()") on an [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection) to get statistics for the connection overall. In this example, a new [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection) is created, and then [`setInterval()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setInterval "setInterval()") is used to set the function `getConnectionStats()` to be called every second.

That function, in turn, uses [`getStats()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/getStats "getStats()") to obtain statistics for the connection and to make use of that data.

    try {
      myPeerConnection = new RTCPeerConnection(pcOptions);

      statsInterval = window.setInterval(getConnectionStats, 1000);
      /* add event handlers, etc */
    } catch(err) {
      console.error("Error creating RTCPeerConnection: " + err);
    }

    function getConnectionStats() {
      myPeerConnection.getStats(null).then(stats => {
        var statsOutput = "";

        stats.forEach(report => {
          if (report.type === "inbound-rtp" && report.kind === "video") {
            Object.keys(report).forEach(statName => {
              statsOutput += `<strong>${statName}:</strong> ${report[statName]}<br>\n`;
            });
          }
        });

        document.querySelector(".stats-box").innerHTML = statsOutput;
      });
    }

When the promise returned by `getStats()` is fulfilled, the resolution handler receives as input an [`RTCStatsReport`](https://developer.mozilla.org/en-US/docs/Web/API/RTCStatsReport) object containing the statistics information. This object contains a [`Map`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map) of named dictionaries based on [`RTCStats`](https://developer.mozilla.org/en-US/docs/Web/API/RTCStats) and its affiliated types.

This example specifically looks for the report whose [`type`](https://developer.mozilla.org/en-US/docs/Web/API/RTCStats/type "type") is `inbound-rtp` and whose [`kind`](https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpStreamStats/kind "kind") is `video`. This way, we look only at the video-related statistics for the local [`RTCRtpReceiver`](https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpReceiver) responsible for receiving the streamed media.

[Commonly used statistics](#commonly_used_statistics "Permalink to Commonly used statistics")
---------------------------------------------------------------------------------------------

[Reference](#reference "Permalink to Reference")
------------------------------------------------

The [`RTCStatsReport`](https://developer.mozilla.org/en-US/docs/Web/API/RTCStatsReport) object contains a map of named objects based one of the [`RTCStats`](https://developer.mozilla.org/en-US/docs/Web/API/RTCStats) dictionary's subclasses. Upon looking up a statistic category by name, you get an object containing the corresponding data. The table below shows the statistic categories and the corresponding dictionaries; for each statistic category, the full hierarchy of `RTCStats`-based dictionaries are listed, so you can easily find all the available values.

<table><caption>Mapping of statistic category names to the dictionaries they implement</caption><colgroup><col style="width: 33%" /><col style="width: 33%" /><col style="width: 33%" /></colgroup><thead><tr class="header"><th>Statistic category name (<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCStatsType"><code>RTCStatsType</code></a>)</th><th>Description</th><th>Dictionaries implemented</th></tr></thead><tbody><tr class="odd"><td><code>candidate-pair</code></td><td>Statistics describing the change from one <a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport"><code>RTCIceTransport</code></a> to another, such as during an <a href="https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Session_lifetime#ice_restart">ICE restart</a>.</td><td><ul><li><a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePairStats"><code>RTCIceCandidatePairStats</code></a><ul><li><a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCStats"><code>RTCStats</code></a></li></ul></li></ul></td></tr><tr class="even"><td><code>certificate</code></td><td>Statistics about a certificate being used by an <a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport"><code>RTCIceTransport</code></a>.</td><td><ul><li><span class="page-not-created"><code>RTCCertificateStats</code></span><ul><li><a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCStats"><code>RTCStats</code></a></li></ul></li></ul></td></tr><tr class="odd"><td><code>codec</code></td><td>Statistics about a specific codec being used by streams being sent or received by this connection.</td><td><span class="page-not-created"><code>RTCCodecStats</code></span><br />
<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCStats"><code>RTCStats</code></a></td></tr><tr class="even"><td><code>csrc</code></td><td>Statistics for a single contributing source (CSRC) that contributed to one of the connection's inbound RTP streams.</td><td><ul><li><span class="page-not-created"><code>RTCRtpContributingSourceStats</code></span><ul><li><a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCStats"><code>RTCStats</code></a></li></ul></li></ul></td></tr><tr class="odd"><td><code>data-channel</code></td><td>Statistics related to one <a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel"><code>RTCDataChannel</code></a> on the connection.</td><td><ul><li><span class="page-not-created"><code>RTCDataChannelStats</code></span><ul><li><a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCStats"><code>RTCStats</code></a></li></ul></li></ul></td></tr><tr class="even"><td><code>ice-server</code></td><td>Statistics about the connection to an <a href="https://developer.mozilla.org/en-US/docs/Glossary/ICE">ICE</a> server (<a href="https://developer.mozilla.org/en-US/docs/Glossary/STUN">STUN</a> or <a href="https://developer.mozilla.org/en-US/docs/Glossary/TURN">TURN</a>.</td><td><ul><li><span class="page-not-created"><code>RTCIceServerStats</code></span><ul><li><a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCStats"><code>RTCStats</code></a></li></ul></li></ul></td></tr><tr class="odd"><td><code>inbound-rtp</code></td><td>Statistics describing the state of one of the connection's inbound data streams.</td><td><ul><li><a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCInboundRtpStreamStats"><code>RTCInboundRtpStreamStats</code></a><ul><li><span class="page-not-created"><code>RTCReceivedRtpStreamStats</code></span><ul><li><a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpStreamStats"><code>RTCRtpStreamStats</code></a><ul><li><a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCStats"><code>RTCStats</code></a></li></ul></li></ul></li></ul></li></ul></td></tr><tr class="even"><td><code>local-candidate</code></td><td>Statistics about a local ICE candidate associated with the connection's <a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport"><code>RTCIceTransport</code></a>s.</td><td><ul><li><a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidateStats"><code>RTCIceCandidateStats</code></a><ul><li><a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCStats"><code>RTCStats</code></a></li></ul></li></ul></td></tr><tr class="odd"><td><code>media-source</code></td><td>Statistics about the media produced by the <a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack"><code>MediaStreamTrack</code></a> attached to an RTP sender. The dictionary this key maps to depends on the track's <a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/kind" title="kind"><code>kind</code></a>.</td><td><ul><li><span class="page-not-created"><code>RTCAudioSourceStats</code></span> <em>or</em> <span class="page-not-created"><code>RTCVideoSourceStats</code></span><ul><li><span class="page-not-created"><code>RTCMediaSourceStats</code></span><ul><li><a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCStats"><code>RTCStats</code></a></li></ul></li></ul></li></ul><span class="page-not-created"><code>RTCAudioSourceStats</code></span> <em>or</em> <span class="page-not-created"><code>RTCVideoSourceStats</code></span></td></tr><tr class="even"><td><code>outbound-rtp</code></td><td>Statistics describing the state of one of the outbound data streams on this connection.</td><td><ul><li><a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCOutboundRtpStreamStats"><code>RTCOutboundRtpStreamStats</code></a><ul><li><span class="page-not-created"><code>RTCSentRtpStreamStats</code></span><ul><li><a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpStreamStats"><code>RTCRtpStreamStats</code></a><ul><li><a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCStats"><code>RTCStats</code></a></li></ul></li></ul></li></ul></li></ul></td></tr><tr class="odd"><td><code>peer-connection</code></td><td>Statistics describing the state of the <a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection"><code>RTCPeerConnection</code></a>.</td><td><ul><li><span class="page-not-created"><code>RTCPeerConnectionStats</code></span><ul><li><a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCStats"><code>RTCStats</code></a></li></ul></li></ul></td></tr><tr class="even"><td><code>receiver</code></td><td>Statistics related to a specific <a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpReceiver"><code>RTCRtpReceiver</code></a> and the media associated with that receiver. The specific type of object representing the statistics depends on the media <code>kind</code>.</td><td><ul><li><span class="page-not-created"><code>RTCAudioReceiverStats</code></span> <em>or</em> <span class="page-not-created"><code>RTCVideoReceiverStats</code></span><ul><li><span class="page-not-created"><code>RTCAudioHandlerStats</code></span> <em>or</em> <span class="page-not-created"><code>RTCVideoHandlerStats</code></span><ul><li><span class="page-not-created"><code>RTCMediaHandlerStats</code></span><ul><li><a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCStats"><code>RTCStats</code></a></li></ul></li></ul></li></ul></li></ul></td></tr><tr class="odd"><td><code>remote-candidate</code></td><td>Statistics about a remote ICE candidate associated with the connection's <a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport"><code>RTCIceTransport</code></a>s.</td><td><ul><li><a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidateStats"><code>RTCIceCandidateStats</code></a><ul><li><a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCStats"><code>RTCStats</code></a></li></ul></li></ul></td></tr><tr class="even"><td><code>remote-inbound-rtp</code></td><td>Statistics describing the state of the inbound data stream from the perspective of the remote peer.</td><td><ul><li><span class="page-not-created"><code>RTCRemoteInboundRtpStreamStats</code></span><ul><li><span class="page-not-created"><code>RTCReceivedRtpStreamStats</code></span><ul><li><a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpStreamStats"><code>RTCRtpStreamStats</code></a><ul><li><a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCStats"><code>RTCStats</code></a></li></ul></li></ul></li></ul></li></ul></td></tr><tr class="odd"><td><code>remote-outbound-rtp</code></td><td>Statistics describing the state of the outbound data stream from the perpsective of the remote peer.</td><td><ul><li><a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRemoteOutboundRtpStreamStats"><code>RTCRemoteOutboundRtpStreamStats</code></a><ul><li><span class="page-not-created"><code>RTCSentRtpStreamStats</code></span><ul><li><a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpStreamStats"><code>RTCRtpStreamStats</code></a><ul><li><a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCStats"><code>RTCStats</code></a></li></ul></li></ul></li></ul></li></ul></td></tr><tr class="even"><td><code>sctp-transport</code></td><td>Statistics about an <a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCSctpTransport"><code>RTCSctpTransport</code></a>.</td><td><ul><li><span class="page-not-created"><code>RTCSctpTransportStats</code></span><ul><li><a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCStats"><code>RTCStats</code></a></li></ul></li></ul></td></tr><tr class="odd"><td><code>sender</code></td><td>Statistics related to a specific <a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpSender"><code>RTCRtpSender</code></a> and the media associated with that sender. The type of object representing this statistic depends on the <code>kind</code> of the media.</td><td><ul><li><span class="page-not-created"><code>RTCAudioSenderStats</code></span> <em>or</em> <span class="page-not-created"><code>RTCVideoSenderStats</code></span><ul><li><span class="page-not-created"><code>RTCAudioHandlerStats</code></span> <em>or</em> <span class="page-not-created"><code>RTCVideoHandlerStats</code></span><ul><li><span class="page-not-created"><code>RTCMediaHandlerStats</code></span><ul><li><a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCStats"><code>RTCStats</code></a></li></ul></li></ul></li></ul></li></ul></td></tr><tr class="even"><td><code>stream</code></td><td>Statistics about a particular media <a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStream"><code>MediaStream</code></a>. This has been obsoleted since the transition to WebRTC being track-based rather than stream-based.</td><td><ul><li><span class="page-not-created"><code>RTCMediaStreamStats</code></span><ul><li><a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCStats"><code>RTCStats</code></a></li></ul></li></ul></td></tr><tr class="odd"><td><code>track</code></td><td><p>Statistics related to a specific <a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack"><code>MediaStreamTrack</code></a>'s attachment to one of the connection's senders or receivers. The referenced object's type depends on the track type.</p><div class="notecard note"><p>These statistics have all been moved to <code>media-source</code>, <code>sender</code>, <code>receiver</code>, <code>outbound-rtp</code>, and <code>inbound-rtp</code>, and this statistic category type is thus obsolete and shouldn't be used anymore.</p></div></td><td><ul><li><span class="page-not-created"><code>RTCSenderVideoTrackAttachmentStats</code></span> <em>or</em> <span class="page-not-created"><code>RTCSenderAudioTrackAttachmentStats</code></span> <em>or</em> <span class="page-not-created"><code>RTCReceiverVideoTrackAttachmentStats</code></span> <em>or</em> <span class="page-not-created"><code>RTCReceiverAudioTrackAttachmentStats</code></span><ul><li><span class="page-not-created"><code>RTCMediaHandlerStats</code></span><ul><li><a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCStats"><code>RTCStats</code></a></li></ul></li></ul></li></ul></td></tr><tr class="even"><td><code>transceiver</code></td><td>Statistics related to a specific <a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpTransceiver"><code>RTCRtpTransceiver</code></a>.</td><td><ul><li><span class="page-not-created"><code>RTCRtpTransceiverStats</code></span><ul><li><a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCStats"><code>RTCStats</code></a></li></ul></li></ul></td></tr><tr class="odd"><td><code>transport</code></td><td>Statistics about a transport used by the connection.</td><td><ul><li><span class="page-not-created"><code>RTCTransportStats</code></span><ul><li><a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCStats"><code>RTCStats</code></a></li></ul></li></ul></td></tr></tbody></table>

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcstatstype" class="external">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'WebRTC statistics types' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Compatibility for individual statistic types</td></tr><tr class="even"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcstatsreport" class="external">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCStatsReport' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Compatibility of statistic reporting</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

No compatibility data found for `api.RTCStatsType`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/webrtc_statistics_api/index.html "Folder: en-us/web/api/webrtc_statistics_api (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWebRTC_Statistics_API%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fwebrtc_statistics_api%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWebRTC_Statistics_API%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fwebrtc_statistics_api%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Ff2a9cd26197733d09c0547ce7d750c65ca59a812%0A*+Document+last+modified%3A+2021-04-27T06%3A37%3A39.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22WebRTC+Statistics+API%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Apr 27, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_Statistics_API/contributors.txt)

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
