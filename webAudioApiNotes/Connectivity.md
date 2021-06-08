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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API" class="breadcrumb-penultimate"><span data-property="name">WebRTC API</span></a>
4.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Connectivity" class="breadcrumb-current-page"><span data-property="name">WebRTC connectivity</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Signaling](#signaling)
-   [ICE candidates](#ice_candidates)
-   [When things go wrong](#when_things_go_wrong)
-   [The entire exchange in a complicated diagram](#the_entire_exchange_in_a_complicated_diagram)

WebRTC connectivity
===================

#### Draft

This page is not complete.

<span class="seoSummary">This article describes how the various WebRTC-related protocols interact with one another in order to create a connection and transfer data and/or media among peers.</span>

**Note:** This page needs heavy rewriting for structural integrity and content completeness. Lots of info here is good but the organization is a mess since this is sort of a dumping ground right now.

[Signaling](#signaling "Permalink to Signaling")
------------------------------------------------

Unfortunately, WebRTC can’t create connections without some sort of server in the middle. We call this the **signal channel** or **signaling service**. It’s any sort of channel of communication to exchange information before setting up a connection, whether by email, post card or a carrier pigeon... it’s up to you.

The information we need to exchange is the Offer and Answer which just contains the [SDP](https://developer.mozilla.org/en-US/docs/Glossary/SDP) mentioned below.

Peer A who will be the initiator of the connection, will create an Offer. They will then send this offer to Peer B using the chosen signal channel. Peer B will receive the Offer from the signal channel and create an Answer. They will then send this back to Peer A along the signal channel.

### [Session descriptions](#session_descriptions "Permalink to Session descriptions")

The configuration of an endpoint on a WebRTC connection is called a **session description**. The description includes information about the kind of media being sent, its format, the transfer protocol being used, the endpoint's IP address and port, and other information needed to describe a media transfer endpoint. This information is exchanged and stored using **Session Description Protocol** ([SDP](https://developer.mozilla.org/en-US/docs/Glossary/SDP)); if you want details on the format of SDP data, you can find it in <a href="https://tools.ietf.org/html/rfc2327" class="external">RFC 2327</a>.

When a user starts a WebRTC call to another user, a special description is created called an **offer**. This description includes all the information about the caller's proposed configuration for the call. The recipient then responds with an **answer**, which is a description of their end of the call. In this way, both devices share with one another the information needed in order to exchange media data. This exchange is handled using Interactive Connectivity Establishment ([ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE)), a protocol which lets two devices use an intermediary to exchange offers and answers even if the two devices are separated by Network Address Translation ([NAT](https://developer.mozilla.org/en-US/docs/Glossary/NAT)).

Each peer, then, keeps two descriptions on hand: the **local description**, describing itself, and the **remote description**, describing the other end of the call.

The offer/answer process is performed both when a call is first established, but also any time the call's format or other configuration needs to change. Regardless of whether it's a new call, or reconfiguring an existing one, these are the basic steps which must occur to exchange the offer and answer, leaving out the ICE layer for the moment:

1.  The caller captures local Media via [`MediaDevices.getUserMedia`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getUserMedia) 
2.  The caller creates `RTCPeerConnection` and calls [`RTCPeerConnection.addTrack()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/addTrack) (Since `addStream` is deprecating)
3.  The caller calls [`RTCPeerConnection.createOffer()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/createOffer) to create an offer.
4.  The caller calls [`RTCPeerConnection.setLocalDescription()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/setLocalDescription) to set that offer as the *local description* (that is, the description of the local end of the connection).
5.  After setLocalDescription(), the caller asks STUN servers to generate the ice candidates
6.  The caller uses the signaling server to transmit the offer to the intended receiver of the call.
7.  The recipient receives the offer and calls [`RTCPeerConnection.setRemoteDescription()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/setRemoteDescription) to record it as the *remote description* (the description of the other end of the connection).
8.  The recipient does any setup it needs to do for its end of the call: capture its local media, and attach each media tracks into the peer connection via [`RTCPeerConnection.addTrack()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/addTrack)
9.  The recipient then creates an answer by calling [`RTCPeerConnection.createAnswer()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/createAnswer).
10. The recipient calls [`RTCPeerConnection.setLocalDescription()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/setLocalDescription), passing in the created answer, to set the answer as its local description. The recipient now knows the configuration of both ends of the connection.
11. The recipient uses the signaling server to send the answer to the caller.
12. The caller receives the answer.
13. The caller calls [`RTCPeerConnection.setRemoteDescription()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/setRemoteDescription) to set the answer as the remote description for its end of the call. It now knows the configuration of both peers. Media begins to flow as configured.

### [Pending and current descriptions](#pending_and_current_descriptions "Permalink to Pending and current descriptions")

Taking one step deeper into the process, we find that `localDescription` and `remoteDescription`, the properties which return these two descriptions, aren't as simple as they look. Because during renegotiation, an offer might be rejected because it proposes an incompatible format, it's necessary that each endpoint have the ability to propose a new format but not actually switch to it until it's accepted by the other peer. For that reason, WebRTC uses *pending* and *current* descriptions.

The **current description** (which is returned by the [`RTCPeerConnection.currentLocalDescription`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/currentLocalDescription) and [`RTCPeerConnection.currentRemoteDescription`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/currentRemoteDescription) properties) represents the description currently in actual use by the connection. This is the most recent connection that both sides have fully agreed to use.

The **pending description** (returned by [`RTCPeerConnection.pendingLocalDescription`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/pendingLocalDescription) and [`RTCPeerConnection.pendingRemoteDescription`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/pendingRemoteDescription)) indicates a description which is currently under consideration following a call to  `setLocalDescription()` or `setRemoteDescription()`, respectively.

When reading the description (returned by [`RTCPeerConnection.localDescription`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/localDescription) and [`RTCPeerConnection.remoteDescription`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/remoteDescription)), the returned value is the value of `pendingLocalDescription`/`pendingRemoteDescription` if there's a pending description (that is, the pending description isn't `null`); otherwise, the current description (`currentLocalDescription`/`currentRemoteDescription`) is returned.

When changing the description by calling `setLocalDescription()` or `setRemoteDescription()`, the specified description is set as the pending description, and the WebRTC layer begins to evaluate whether or not it's acceptable. Once the proposed description has been agreed upon, the value of `currentLocalDescription` or `currentRemoteDescription` is changed to the pending description, and the pending description is set to null again, indicating that there isn't a pending description.

The `pendingLocalDescription` contains not just the offer or answer under consideration, but any local ICE candidates which have already been gathered since the offer or answer was created. Similarly, `pendingRemoteDescription` includes any remote ICE candidates which have been provided by calls to [`RTCPeerConnection.addIceCandidate()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/addIceCandidate).

See the individual articles on these properties and methods for more specifics, and [Codecs used by WebRTC](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/WebRTC_codecs) for information about codecs supported by WebRTC and which are compatible with which browsers. The codecs guide also offers guidance to help you choose the best codecs for your needs.

[ICE candidates](#ice_candidates "Permalink to ICE candidates")
---------------------------------------------------------------

As well as exchanging information about the media (discussed above in Offer/Answer and SDP), peers must exchange information about the network connection. This is known as an **ICE candidate** and details the available methods the peer is able to communicate (directly or through a TURN server). Typically, each peer will propose its best candidates first, making their way down the line toward their worse candidates. Ideally, candidates are UDP (since it's faster, and media streams are able to recover from interruptions relatively easily), but the ICE standard does allow TCP candidates as well.

Generally, ICE candidates using TCP are only going to be used when UDP is not available or is restricted in ways that make it not suitable for media streaming. Not all browsers support ICE over TCP, however.

ICE allows candidates to represent connections over either [TCP](https://developer.mozilla.org/en-US/docs/Glossary/TCP) or [UDP](https://developer.mozilla.org/en-US/docs/Glossary/UDP), with UDP generally being preferred (and being more widely supported). Each protocol supports a few types of candidate, with the candidate types defining how the data makes its way from peer to peer.

### [UDP candidate types](#udp_candidate_types "Permalink to UDP candidate types")

UDP candidates (candidates with their [`protocol`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/protocol "protocol") set to `udp`) can be one of these types:

`host`  
A host candidate is one for which its [`ip`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/address "ip") address is the actual, direct IP address of the remote peer.

`prflx`  
A peer reflexive candidate is one whose IP address comes from a symmetric NAT between the two peers, usually as an additional candidate during trickle ICE (that is, additional candidate exchanges that occur after primary signaling but before the connection verification phase is finished).

`srflx`  
A server reflexive candidate is generated by a STUN/TURN server; the connection's initiator requests a candidate from the STUN server, which forwards the request through the remote peer's NAT, which creates and returns a candidate whose IP address is local to the remote peer. The STUN server then replies to the initiator's request with a candidate whose IP address is unrelated to the remote peer.

`relay`  
A relay candidate is generated just like a server reflexive candidate (`"srflx"`), but using [TURN](https://developer.mozilla.org/en-US/docs/Glossary/TURN) instead of [STUN](https://developer.mozilla.org/en-US/docs/Glossary/STUN).

### [TCP candidate types](#tcp_candidate_types "Permalink to TCP candidate types")

TCP candidates (that is, candidates whose [`protocol`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/protocol "protocol") is `tcp`) can be of these types:

`active`  
The transport will try to open an outbound connection but won't receive incoming connection requests. This is the most common type, and the only one that most user agents will gather.

`passive`  
The transport will receive incoming connection attempts but won't attempt a connection itself.

`so`  
The transport will try to simultaneously open a connection with its peer.

### [Choosing a candidate pair](#choosing_a_candidate_pair "Permalink to Choosing a candidate pair")

The ICE layer selects one of the two peers to serve as the **controlling agent**. This is the ICE agent which will make the final decision as to which candidate pair to use for the connection. The other peer is called the **controlled agent**. You can identify which one your end of the connection is by examining the value of [`RTCIceCandidate.transport.role`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/role "RTCIceCandidate.transport.role"), although in general it doesn't matter which is which.

The controlling agent not only takes responsibility for making the final decision as to which candidate pair to use, but also for signaling that selection to the controlled agent by using STUN and an updated offer, if necessary. The controlled agent just waits to be told which candidate pair to use.

It's important to keep in mind that a single ICE session may result in the controlling agent choosing more than one candidate pair. Each time it does so and shares that information with the controlled agent, the two peers reconfigure their connection to use the new configuration described by the new candidate pair.

Once the ICE session is complete, the configuration that's currently in effect is the final one, unless an ICE reset occurs.

At the end of each generation of candidates, an end-of-candidates notification is sent in the form of an [`RTCIceCandidate`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate) whose [`candidate`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/candidate "candidate") property is an empty string. This candidate should still be added to the connection using [`addIceCandidate()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/addIceCandidate "addIceCandidate()") method, as usual, in order to deliver that notification to the remote peer.

When there are no more candidates at all to be expected during the current negotiation exchange, an end-of-candidates notification is sent by delivering a [`RTCIceCandidate`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate) whose [`candidate`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/candidate "candidate") property is `null`. This message does *not* need to be sent to the remote peer. It's a legacy notification of a state which can be detected instead by watching for the [`iceGatheringState`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/iceGatheringState "iceGatheringState") to change to `complete`, by watching for the [`icegatheringstatechange`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/icegatheringstatechange_event "icegatheringstatechange") event.

[When things go wrong](#when_things_go_wrong "Permalink to When things go wrong")
---------------------------------------------------------------------------------

During negotiation, there will be times when things just don't work out. For example, when renegotiating a connection—for example, to adapt to changing hardware or network configurations—it's possible that negotiation could reach a dead end, or some form of error might occur that prevents negotiation at all. There may be permissions issues or other problems as well, for that matter.

### [ICE rollbacks](#ice_rollbacks "Permalink to ICE rollbacks")

When renegotiating a connection that's already active and a situation arises in which the negotiation fails, you don't really want to kill the already-running call. After all, you were most likely just trying to upgrade or downgrade the connection, or to otherwise make adaptations to an ongoing session. Aborting the call would be an excessive reaction in that situation.

Instead, you can initiate an **ICE rollback**. A rollback restores the SDP offer (and the connection configuration by extension) to the configuration it had the last time the connection's [`signalingState`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/signalingState "signalingState") was `stable`.

To programmatically initiate a rollback, send a description whose [`type`](https://developer.mozilla.org/en-US/docs/Web/API/RTCSessionDescription/type "type") is `rollback`. Any other properties in the description object are ignored.

In addition, the ICE agent will automatically initiate a rollback when a peer that had previously created an offer receives an offer from the remote peer. In other words, if the local peer is in the state `have-local-offer`, indicating that the local peer had previously *sent* an offer, calling `setRemoteDescription()` with a *received* offer triggers rollback so that the negotiation switches from the remote peer being the caller to the local peer being the caller.

### [ICE restarts](#ice_restarts "Permalink to ICE restarts")

For now, see [ICE restart](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Session_lifetime#ice_restart) in [Lifetime of a WebRTC session](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Session_lifetime).

[The entire exchange in a complicated diagram](#the_entire_exchange_in_a_complicated_diagram "Permalink to The entire exchange in a complicated diagram")
---------------------------------------------------------------------------------------------------------------------------------------------------------

<a href="https://hacks.mozilla.org/wp-content/uploads/2013/07/webrtc-complete-diagram.png" class="external"><img src="https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Connectivity/webrtc-complete-diagram.png" alt="A complete architectural diagram showing the whole WebRTC process." width="641" height="559" /></a>

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/webrtc_api/connectivity/index.html "Folder: en-us/web/api/webrtc_api/connectivity (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWebRTC_API%2FConnectivity%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fwebrtc_api%2Fconnectivity%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWebRTC_API%2FConnectivity%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fwebrtc_api%2Fconnectivity%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F7528e640a129448fb9779755e8151afd124f1aaf%0A*+Document+last+modified%3A+2021-04-02T03%3A03%3A55.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22WebRTC+connectivity%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Apr 2, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Connectivity/contributors.txt)

Change your languageSelect your preferred language English (US)Français日本語Русский中文 (简体)

Change language

#### Related Topics

1.  [**WebRTC API**](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API)
2.  WebRTC Guides
    1.  [WebRTC Architecture](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Architecture)
    2.  [WebRTC Basics](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/WebRTC_Basics)
    3.  [WebRTC Protocols](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Protocols)
    4.  [Dealing with connectivity](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Connectivity)
    5.  [Overview of WebRTC interfaces](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Overview)
    6.  [Lifetime of a WebRTC Session](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Session_lifetime)
    7.  [Using data channels](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Using_data_channels)
3.  WebRTC Tutorials
    1.  [Interoperability with adapter.js](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/adapter.js)
    2.  [Taking still photos from the camera](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Taking_still_photos)
    3.  [A simple data channel example](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Simple_RTCDataChannel_sample)
    4.  [Building an internet-connected phone with Peer.js](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Build_a_phone_with_peerjs)
4.  Interfaces
    1.  [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection)
    2.  [`RTCSessionDescription`](https://developer.mozilla.org/en-US/docs/Web/API/RTCSessionDescription)
    3.  [`RTCIceCandidate`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate)
    4.  [`RTCPeerConnectionIceEvent`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnectionIceEvent)
    5.  [`MessageEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MessageEvent)
    6.  [`MediaStream`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream)
    7.  [`RTCStatsReport`](https://developer.mozilla.org/en-US/docs/Web/API/RTCStatsReport)
    8.  [`RTCIdentityEvent`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIdentityEvent)
    9.  [`RTCIdentityErrorEvent`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIdentityErrorEvent)
    10. [`MediaStreamEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamEvent)
    11. [`MediaStreamTrack`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack)
    12. [`MediaDevices`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices)
5.  **[Documentation:](https://developer.mozilla.org/en-US/docs/MDN)**
6.  Contribute
    1.  [The MDN project](https://developer.mozilla.org/en-US/docs/MDN)

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
