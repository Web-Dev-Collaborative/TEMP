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
3.  <a href="WebRTC_API.html" class="breadcrumb-current-page"><span data-property="name">WebRTC API</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Interoperability](#interoperability)
-   [WebRTC concepts and usage](#webrtc_concepts_and_usage)
-   [WebRTC reference](#webrtc_reference)
-   [Guides](#guides)
-   [Tutorials](#tutorials)
-   [Resources](#resources)
-   [Specifications](#specifications)
-   [See also](#see_also)

WebRTC API
==========

<span class="seoSummary">**WebRTC** (Web Real-Time Communication) is a technology which enables Web applications and sites to capture and optionally stream audio and/or video media, as well as to exchange arbitrary data between browsers without requiring an intermediary.</span> The set of standards that comprise WebRTC makes it possible to share data and perform teleconferencing peer-to-peer, without requiring that the user install plug-ins or any other third-party software.

WebRTC consists of several interrelated APIs and protocols which work together to achieve this. The documentation you'll find here will help you understand the fundamentals of WebRTC, how to set up and use both data and media connections, and more.

[Interoperability](#interoperability "Permalink to Interoperability")
---------------------------------------------------------------------

Because implementations of WebRTC are still evolving, and because each browser has [different levels of support for codecs](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/WebRTC_codecs) and WebRTC features, you should *strongly* consider making use of <a href="https://github.com/webrtcHacks/adapter" class="external">the Adapter.js library</a> provided by Google before you begin to write your code.

Adapter.js uses shims and polyfills to smooth over the differences among the WebRTC implementations across the environments supporting it. Adapter.js also handles prefixes and other naming differences to make the entire WebRTC development process easier, with more broadly compatible results. The library is also <a href="https://www.npmjs.com/package/webrtc-adapter" class="external">available as an NPM package</a>.

To learn more about Adapter.js, see [Improving compatibility using WebRTC adapter.js](WebRTC_API/adapter.html).

[WebRTC concepts and usage](#webrtc_concepts_and_usage "Permalink to WebRTC concepts and usage")
------------------------------------------------------------------------------------------------

WebRTC serves multiple purposes; together with the [Media Capture and Streams API](Media_Streams_API.html), they provide powerful multimedia capabilities to the Web, including support for audio and video conferencing, file exchange, screen sharing, identity management, and interfacing with legacy telephone systems including support for sending [DTMF](https://developer.mozilla.org/en-US/docs/Glossary/DTMF) (touch-tone dialing) signals. Connections between peers can be made without requiring any special drivers or plug-ins, and can often be made without any intermediary servers.

Connections between two peers are represented by the [`RTCPeerConnection`](RTCPeerConnection.html) interface. Once a connection has been established and opened using `RTCPeerConnection`, media streams ([`MediaStream`](MediaStream.html)s) and/or data channels ([`RTCDataChannel`](RTCDataChannel.html)s) can be added to the connection.

Media streams can consist of any number of tracks of media information; tracks, which are represented by objects based on the [`MediaStreamTrack`](MediaStreamTrack.html) interface, may contain one of a number of types of media data, including audio, video, and text (such as subtitles or even chapter names). Most streams consist of at least one audio track and likely also a video track, and can be used to send and receive both live media or stored media information (such as a streamed movie).

You can also use the connection between two peers to exchange arbitrary binary data using the [`RTCDataChannel`](RTCDataChannel.html) interface. This can be used for back-channel information, metadata exchange, game status packets, file transfers, or even as a primary channel for data transfer.

***more details and links to relevant guides and tutorials needed***

[WebRTC reference](#webrtc_reference "Permalink to WebRTC reference")
---------------------------------------------------------------------

Because WebRTC provides interfaces that work together to accomplish a variety of tasks, we have divided up the reference by category. Please see the sidebar for an alphabetical list.

### [Connection setup and management](#connection_setup_and_management "Permalink to Connection setup and management")

These interfaces, dictionaries, and types are used to set up, open, and manage WebRTC connections. Included are interfaces representing peer media connections, data channels, and interfaces used when exchanging information on the capabilities of each peer in order to select the best possible configuration for a two-way media connection.

#### Interfaces

[`RTCPeerConnection`](RTCPeerConnection.html)  
Represents a WebRTC connection between the local computer and a remote peer. It is used to handle efficient streaming of data between the two peers.

[`RTCDataChannel`](RTCDataChannel.html)  
Represents a bi-directional data channel between two peers of a connection.

[`RTCDataChannelEvent`](RTCDataChannelEvent.html)  
Represents events that occur while attaching a [`RTCDataChannel`](RTCDataChannel.html) to a [`RTCPeerConnection`](RTCPeerConnection.html). The only event sent with this interface is `datachannel`.

[`RTCSessionDescription`](RTCSessionDescription.html)  
Represents the parameters of a session. Each `RTCSessionDescription` consists of a description [`type`](RTCSessionDescription/type.html "type") indicating which part of the offer/answer negotiation process it describes and of the [SDP](https://developer.mozilla.org/en-US/docs/Glossary/SDP) descriptor of the session.

[`RTCStatsReport`](RTCStatsReport.html)  
Provides information detailing statistics for a connection or for an individual track on the connection; the report can be obtained by calling [`RTCPeerConnection.getStats()`](RTCPeerConnection/getStats.html). Details about using WebRTC statistics can be found in [WebRTC Statistics API](WebRTC_Statistics_API.html).

[`RTCIceCandidate`](RTCIceCandidate.html)  
Represents a candidate Interactive Connectivity Establishment ([ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE)) server for establishing an [`RTCPeerConnection`](RTCPeerConnection.html).

[`RTCIceTransport`](RTCIceTransport.html)  
Represents information about an [ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE) transport.

[`RTCPeerConnectionIceEvent`](RTCPeerConnectionIceEvent.html)  
Represents events that occur in relation to ICE candidates with the target, usually an [`RTCPeerConnection`](RTCPeerConnection.html). Only one event is of this type: `icecandidate`.

[`RTCRtpSender`](RTCRtpSender.html)  
Manages the encoding and transmission of data for a [`MediaStreamTrack`](MediaStreamTrack.html) on an [`RTCPeerConnection`](RTCPeerConnection.html).

[`RTCRtpReceiver`](RTCRtpReceiver.html)  
Manages the reception and decoding of data for a [`MediaStreamTrack`](MediaStreamTrack.html) on an [`RTCPeerConnection`](RTCPeerConnection.html).

[`RTCTrackEvent`](RTCTrackEvent.html)  
The interface used to represent a [`track`](RTCPeerConnection/track_event.html "track") event, which indicates that an [`RTCRtpReceiver`](RTCRtpReceiver.html) object was added to the [`RTCPeerConnection`](RTCPeerConnection.html) object, indicating that a new incoming [`MediaStreamTrack`](MediaStreamTrack.html) was created and added to the `RTCPeerConnection`.

[`RTCSctpTransport`](RTCSctpTransport.html)  
Provides information which describes a Stream Control Transmission Protocol (**[SCTP](https://developer.mozilla.org/en-US/docs/Glossary/SCTP)**) transport and also provides a way to access the underlying Datagram Transport Layer Security (**[DTLS](https://developer.mozilla.org/en-US/docs/Glossary/DTLS)**) transport over which SCTP packets for all of an [`RTCPeerConnection`](RTCPeerConnection.html "The RTCPeerConnection interface represents a WebRTC connection between the local computer and a remote peer. It provides methods to connect to a remote peer, maintain and monitor the connection, and close the connection once it's no longer needed.")'s data channels are sent and received.

#### Dictionaries

[`RTCConfiguration`](RTCConfiguration.html)  
Used to provide configuration options for an [`RTCPeerConnection`](RTCPeerConnection.html "The RTCPeerConnection interface represents a WebRTC connection between the local computer and a remote peer. It provides methods to connect to a remote peer, maintain and monitor the connection, and close the connection once it's no longer needed.").

[`RTCIceServer`](RTCIceServer.html)  
Defines how to connect to a single [ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE) server (such as a [STUN](https://developer.mozilla.org/en-US/docs/Glossary/STUN) or [TURN](https://developer.mozilla.org/en-US/docs/Glossary/TURN) server).

[`RTCRtpContributingSource`](RTCRtpContributingSource.html)  
Contains information about a given contributing source (CSRC) including the most recent time a packet that the source contributed was played out.

#### Events

[`bufferedamountlow`](RTCDataChannel/bufferedamountlow_event.html "bufferedamountlow")  
The amount of data currently buffered by the data channel—as indicated by its [`bufferedAmount`](RTCDataChannel/bufferedAmount.html "bufferedAmount") property—has decreased to be at or below the channel's minimum buffered data size, as specified by [`bufferedAmountLowThreshold`](RTCDataChannel/bufferedAmountLowThreshold.html "bufferedAmountLowThreshold").

[`close`](RTCDataChannel/close_event.html "close")  
The data channel has completed the closing process and is now in the `closed` state. Its underlying data transport is completely closed at this point. You can be notified *before* closing completes by watching for the `closing` event instead.

[`closing`](RTCDataChannel/closing_event.html "closing")  
The `RTCDataChannel` has transitioned to the `closing` state, indicating that it will be closed soon. You can detect the completion of the closing process by watching for the `close` event.

[`connectionstatechange`](RTCPeerConnection/connectionstatechange_event.html "connectionstatechange")  
The connection's state, which can be accessed in [`connectionState`](RTCPeerConnection/connectionState.html "connectionState"), has changed.

[`datachannel`](RTCPeerConnection/datachannel_event.html "datachannel")  
A new [`RTCDataChannel`](RTCDataChannel.html) is available following the remote peer opening a new data channel. This event's type is [`RTCDataChannelEvent`](RTCDataChannelEvent.html).

[`error`](RTCDataChannel/error_event.html "error")  
An [`RTCErrorEvent`](RTCErrorEvent.html) indicating that an error occurred on the data channel.

[`error`](RTCDtlsTransport/error_event.html "error")  
An [`RTCErrorEvent`](RTCErrorEvent.html) indicating that an error occurred on the [`RTCDtlsTransport`](RTCDtlsTransport.html). This error will be either `dtls-failure` or `fingerprint-failure`.

[`gatheringstatechange`](RTCIceTransport/gatheringstatechange_event.html "gatheringstatechange")  
The [`RTCIceTransport`](RTCIceTransport.html)'s gathering state has changed.

[`icecandidate`](RTCPeerConnection/icecandidate_event.html "icecandidate")  
An [`RTCPeerConnectionIceEvent`](RTCPeerConnectionIceEvent.html) which is sent whenever the local device has identified a new ICE candidate which needs to be added to the local peer by calling [`setLocalDescription()`](RTCPeerConnection/setLocalDescription.html "setLocalDescription()").

[`icecandidateerror`](RTCPeerConnection/icecandidateerror_event.html "icecandidateerror")  
An [`RTCPeerConnectionIceErrorEvent`](RTCPeerConnectionIceErrorEvent.html) indicating that an error has occurred while gathering ICE candidates.

[`iceconnectionstatechange`](RTCPeerConnection/iceconnectionstatechange_event.html "iceconnectionstatechange")  
Sent to an [`RTCPeerConnection`](RTCPeerConnection.html) when its ICE connection's state—found in the [`iceconnectionstate`](RTCPeerConnection/iceConnectionState.html "iceconnectionstate") property—changes.

[`icegatheringstatechange`](RTCPeerConnection/icegatheringstatechange_event.html "icegatheringstatechange")  
Sent to an [`RTCPeerConnection`](RTCPeerConnection.html) when its ICE gathering state—found in the [`icegatheringstate`](RTCPeerConnection/iceGatheringState.html "icegatheringstate") property—changes.

[`message`](RTCDataChannel/message_event.html "message")  
A message has been received on the data channel. The event is of type [`MessageEvent`](MessageEvent.html).

[`negotiationneeded`](RTCPeerConnection/negotiationneeded_event.html "negotiationneeded")  
Informs the `RTCPeerConnection` that it needs to perform session negotiation by calling [`createOffer()`](RTCPeerConnection/createOffer.html "createOffer()") followed by [`setLocalDescription()`](RTCPeerConnection/setLocalDescription.html "setLocalDescription()").

[`open`](RTCDataChannel/open_event.html "open")  
The underlying data transport for the `RTCDataChannel` has been successfully opened or re-opened.

[`selectedcandidatepairchange`](RTCIceTransport/selectedcandidatepairchange_event.html "selectedcandidatepairchange")  
The currently-selected pair of ICE candidates has changed for the `RTCIceTransport` on which the event is fired.

[`track`](RTCPeerConnection/track_event.html "track")  
The `track` event, of type [`RTCTrackevent`](RTCTrackEvent.html) is sent to an [`RTCPeerConnection`](RTCPeerConnection.html) when a new track is added to the connection following the successful negotiation of the media's streaming.

[`signalingstatechange`](RTCPeerConnection/signalingstatechange_event.html "signalingstatechange")  
Sent to the peer connection when its [`signalingstate`](RTCPeerConnection/signalingState.html "signalingstate") has changed. This happens as a result of a call to either [`setLocalDescription()`](RTCPeerConnection/setLocalDescription.html "setLocalDescription()") or [`setRemoteDescription()`](RTCPeerConnection/setRemoteDescription.html "setRemoteDescription()").

<span class="page-not-created">`statechange`</span>  
The state of the `RTCDtlsTransport` has changed.

[`statechange`](RTCIceTransport/statechange_event.html "statechange")  
The state of the `RTCIceTransport` has changed.

<span class="page-not-created">`statechange`</span>  
The state of the `RTCSctpTransport` has changed.

#### Types

[`RTCSctpTransport.state`](RTCSctpTransport/state.html)  
Indicates the state of an [`RTCSctpTransport`](RTCSctpTransport.html) instance.

[`RTCSessionDescriptionCallback`](RTCSessionDescriptionCallback.html)  
The RTCSessionDescriptionCallback is passed into the [`RTCPeerConnection`](RTCPeerConnection.html) object when requesting it to create offers or answers.

### [Identity and security](#identity_and_security "Permalink to Identity and security")

These APIs are used to manage user identity and security, in order to authenticate the user for a connection.

<span class="page-not-created">`RTCIdentityProvider`</span>  
Enables a user agent is able to request that an identity assertion be generated or validated.

[`RTCIdentityAssertion`](RTCIdentityAssertion.html)  
Represents the identity of the remote peer of the current connection. If no peer has yet been set and verified this interface returns `null`. Once set it can't be changed.

<span class="page-not-created">`RTCIdentityProviderRegistrar`</span>  
Registers an identity provider (idP).

[`RTCIdentityEvent`](RTCIdentityEvent.html)  
Represents an identity assertion generated by an identity provider (idP). This is usually for an [`RTCPeerConnection`](RTCPeerConnection.html). The only event sent with this type is `identityresult`.

[`RTCIdentityErrorEvent`](RTCIdentityErrorEvent.html)  
Represents an error associated with the identity provider (idP). This is usually for an [`RTCPeerConnection`](RTCPeerConnection.html). Two events are sent with this type: `idpassertionerror` and `idpvalidationerror`.

[`RTCCertificate`](RTCCertificate.html)  
Represents a certificate that an [`RTCPeerConnection`](RTCPeerConnection.html) uses to authenticate.

### [Telephony](#telephony "Permalink to Telephony")

These interfaces and events are related to interactivity with Public-Switched Telephone Networks (PTSNs). They're primarily used to send tone dialing sounds—or packets representing those tones—across the network to the remote peer.

#### Interfaces

[`RTCDTMFSender`](RTCDTMFSender.html)  
Manages the encoding and transmission of Dual-Tone Multi-Frequency ([DTMF](https://developer.mozilla.org/en-US/docs/Glossary/DTMF)) signaling for an [`RTCPeerConnection`](RTCPeerConnection.html).

[`RTCDTMFToneChangeEvent`](RTCDTMFToneChangeEvent.html)  
Used by the [`tonechange`](RTCDTMFSender/tonechange_event.html "tonechange") event to indicate that a DTMF tone has either begun or ended. This event does not bubble (except where otherwise stated) and is not cancelable (except where otherwise stated).

#### Events

[`tonechange`](RTCDTMFSender/tonechange_event.html "tonechange")  
Either a new [DTMF](https://developer.mozilla.org/en-US/docs/Glossary/DTMF) tone has begun to play over the connection, or the last tone in the `RTCDTMFSender`'s [`toneBuffer`](RTCDTMFSender/toneBuffer.html "toneBuffer") has been sent and the buffer is now empty. The event's type is [`RTCDTMFToneChangeEvent`](RTCDTMFToneChangeEvent.html).

[Guides](#guides "Permalink to Guides")
---------------------------------------

[Introduction to WebRTC protocols](WebRTC_API/Protocols.html)  
This article introduces the protocols on top of which the WebRTC API is built.

[WebRTC connectivity](WebRTC_API/Connectivity.html)  
A guide to how WebRTC connections work and how the various protocols and interfaces can be used together to build powerful communication apps.

[Lifetime of a WebRTC session](WebRTC_API/Session_lifetime.html)  
WebRTC lets you build peer-to-peer communication of arbitrary data, audio, or video—or any combination thereof—into a browser application. In this article, we'll look at the lifetime of a WebRTC session, from establishing the connection all the way through closing the connection when it's no longer needed.

[Establishing a connection: The perfect negotiation pattern](WebRTC_API/Perfect_negotiation.html)  
**Perfect negotiation** is a design pattern which is recommended for your signaling process to follow, which provides transparency in negotiation while allowing both sides to be either the offerer or the answerer, without significant coding needed to differentiate the two.

[Signaling and two-way video calling](WebRTC_API/Signaling_and_video_calling.html)  
A tutorial and example which turns a WebSocket-based chat system created for a previous example and adds support for opening video calls among participants. The chat server's WebSocket connection is used for WebRTC signaling.

[Codecs used by WebRTC](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/WebRTC_codecs)  
A guide to the codecs which WebRTC requires browsers to support as well as the optional ones supported by various popular browsers. Included is a guide to help you choose the best codecs for your needs.

[Using WebRTC data channels](WebRTC_API/Using_data_channels.html)  
This guide covers how you can use a peer connection and an associated [`RTCDataChannel`](RTCDataChannel.html) to exchange arbitrary data between two peers.

[Using DTMF with WebRTC](WebRTC_API/Using_DTMF.html)  
WebRTC's support for interacting with gateways that link to old-school telephone systems includes support for sending DTMF tones using the [`RTCDTMFSender`](RTCDTMFSender.html) interface. This guide shows how to do so.

[Tutorials](#tutorials "Permalink to Tutorials")
------------------------------------------------

[Improving compatibility using WebRTC adapter.js](WebRTC_API/adapter.html)  
The WebRTC organization <a href="https://github.com/webrtc/adapter/" class="external">provides on GitHub the WebRTC adapter</a> to work around compatibility issues in different browsers' WebRTC implementations. The adapter is a JavaScript shim which lets your code to be written to the specification so that it will "just work" in all browsers with WebRTC support.

[Taking still photos with WebRTC](WebRTC_API/Taking_still_photos.html)  
This article shows how to use WebRTC to access the camera on a computer or mobile phone with WebRTC support and take a photo with it.

[A simple RTCDataChannel sample](WebRTC_API/Simple_RTCDataChannel_sample.html)  
The [`RTCDataChannel`](RTCDataChannel.html) interface is a feature which lets you open a channel between two peers over which you may send and receive arbitrary data. The API is intentionally similar to the [WebSocket API](WebSockets_API.html), so that the same programming model can be used for each.

[Building an internet connected phone with Peer.js](WebRTC_API/Build_a_phone_with_peerjs.html)  
This tutorial is a step-by-step guide on how to build a phone using Peer.js

[Resources](#resources "Permalink to Resources")
------------------------------------------------

### [Protocols](#protocols "Permalink to Protocols")

#### WebRTC-proper protocols

-   <a href="https://datatracker.ietf.org/doc/draft-ietf-rtcweb-alpn/" class="external">Application Layer Protocol Negotiation for Web Real-Time Communications</a>
-   <a href="https://datatracker.ietf.org/doc/draft-ietf-rtcweb-audio/" class="external">WebRTC Audio Codec and Processing Requirements</a>
-   <a href="https://datatracker.ietf.org/doc/draft-ietf-rtcweb-data-channel/" class="external">RTCWeb Data Channels</a>
-   <a href="https://datatracker.ietf.org/doc/draft-ietf-rtcweb-data-protocol/" class="external">RTCWeb Data Channel Protocol</a>
-   <a href="https://datatracker.ietf.org/doc/draft-ietf-rtcweb-rtp-usage/" class="external">Web Real-Time Communication (WebRTC): Media Transport and Use of RTP</a>
-   <a href="https://datatracker.ietf.org/doc/draft-ietf-rtcweb-security-arch/" class="external">WebRTC Security Architecture</a>
-   <a href="https://datatracker.ietf.org/doc/draft-ietf-rtcweb-transports/" class="external">Transports for RTCWEB</a>

#### Related supporting protocols

-   <a href="https://datatracker.ietf.org/doc/html/rfc5245" class="external">Interactive Connectivity Establishment (ICE): A Protocol for Network Address Translator (NAT) Traversal for Offer/Answer Protocol</a>
-   <a href="https://datatracker.ietf.org/doc/html/rfc5389" class="external">Session Traversal Utilities for NAT (STUN)</a>
-   <a href="https://datatracker.ietf.org/doc/html/rfc7064" class="external">URI Scheme for the Session Traversal Utilities for NAT (STUN) Protocol</a>
-   <a href="https://datatracker.ietf.org/doc/html/rfc7065" class="external">Traversal Using Relays around NAT (TURN) Uniform Resource Identifiers</a>
-   <a href="https://datatracker.ietf.org/doc/html/rfc3264" class="external">An Offer/Answer Model with Session Description Protocol (SDP)</a>
-   <a href="https://datatracker.ietf.org/doc/draft-ietf-tram-turn-third-party-authz/" class="external">Session Traversal Utilities for NAT (STUN) Extension for Third Party Authorization</a>

#### WebRTC statistics

-   [WebRTC Statistics API](WebRTC_Statistics_API.html)

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/" class="external" title="The &#39;WebRTC 1.0: Real-time Communication Between Browsers&#39; specification">WebRTC 1.0: Real-time Communication Between Browsers</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>The initial definition of the API of WebRTC.</td></tr><tr class="even"><td><a href="https://w3c.github.io/mediacapture-main/" class="external" title="The &#39;Media Capture and Streams&#39; specification">Media Capture and Streams</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>The initial definition of the object conveying the stream of media content.</td></tr><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-fromelement/" class="external" title="The &#39;Media Capture from DOM Elements&#39; specification">Media Capture from DOM Elements</a></td><td><span class="spec-wd">Working Draft</span></td><td>The initial definition on how to obtain stream of content from DOM Elements</td></tr></tbody></table>

In additions to these specifications defining the API needed to use WebRTC, there are several protocols, listed under [resources](#protocols).

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [`MediaDevices`](MediaDevices.html)
-   [`MediaStreamEvent`](MediaStreamEvent.html)
-   [`MediaStreamConstraints`](MediaStreamConstraints.html)
-   [`MediaStreamTrack`](MediaStreamTrack.html)
-   [`MessageEvent`](MessageEvent.html)
-   [`MediaStream`](MediaStream.html)
-   [Media Capture and Streams API](Media_Streams_API.html)
-   <a href="https://hacks.mozilla.org/2015/06/firefox-multistream-and-renegotiation-for-jitsi-videobridge/" class="external">Firefox multistream and renegotiation for Jitsi Videobridge</a>
-   <a href="https://hacks.mozilla.org/2015/04/peering-through-the-webrtc-fog-with-socketpeer/" class="external">Peering Through the WebRTC Fog with SocketPeer</a>
-   <a href="https://hacks.mozilla.org/2014/04/inside-the-party-bus-building-a-web-app-with-multiple-live-video-streams-interactive-graphics/" class="external">Inside the Party Bus: Building a Web App with Multiple Live Video Streams + Interactive Graphics</a>
-   [Web media technologies](https://developer.mozilla.org/en-US/docs/Web/Media)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/webrtc_api/index.html "Folder: en-us/web/api/webrtc_api (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWebRTC_API%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fwebrtc_api%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWebRTC_API%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fwebrtc_api%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fba4a07195d8f8f4941e7ae06118b8405f9cac9cf%0A*+Document+last+modified%3A+2021-04-10T23%3A58%3A36.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22WebRTC+API%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Apr 10, 2021, [by MDN contributors](WebRTC_API/contributors.txt)

Change your languageSelect your preferred language English (US)EspañolFrançais日本語한국어Português (do Brasil)Русский中文 (简体)正體中文 (繁體)

Change language

#### Related Topics

1.  **[WebRTC API](WebRTC_API.html)**
2.  Guides
    1.  [Introduction to WebRTC protocols](WebRTC_API/Protocols.html)
    2.  [WebRTC connectivity](WebRTC_API/Connectivity.html)
    3.  [Lifetime of a WebRTC session](WebRTC_API/Session_lifetime.html)
    4.  [Signaling and video calling](WebRTC_API/Signaling_and_video_calling.html)
    5.  [Using WebRTC data channels](WebRTC_API/Using_data_channels.html)
    6.  [Using DTMF with WebRTC](WebRTC_API/Using_DTMF.html)
    7.  [Improving compatibility using WebRTC adapter.js](WebRTC_API/adapter.html)
    8.  [Taking still photos with WebRTC](WebRTC_API/Taking_still_photos.html)
    9.  [A simple RTCDataChannel sample](WebRTC_API/Simple_RTCDataChannel_sample.html)
3.  Interfaces
    1.  [`RTCPeerConnection`](RTCPeerConnection.html)
    2.  [`RTCSessionDescription`](RTCSessionDescription.html)
    3.  [`RTCIceCandidate`](RTCIceCandidate.html)
    4.  [`RTCPeerConnectionIceEvent`](RTCPeerConnectionIceEvent.html)
    5.  [`RTCPeerConnectionIceErrorEvent`](RTCPeerConnectionIceErrorEvent.html)
    6.  [`RTCCertificate`](RTCCertificate.html)
    7.  [`RTCRtpSender`](RTCRtpSender.html)
    8.  [`RTCRtpReceiver`](RTCRtpReceiver.html)
    9.  [`RTCRtpTransceiver`](RTCRtpTransceiver.html)
    10. [`RTCDtlsTransport`](RTCDtlsTransport.html)
    11. [`RTCIceTransport`](RTCIceTransport.html)
    12. [`RTCTrackEvent`](RTCTrackEvent.html)
    13. [`RTCSctpTransport`](RTCSctpTransport.html)
    14. [`RTCDataChannel`](RTCDataChannel.html)
    15. [`RTCDataChannelEvent`](RTCDataChannelEvent.html)
    16. [`RTCDTMFSender`](RTCDTMFSender.html)
    17. [`RTCDTMFToneChangeEvent`](RTCDTMFToneChangeEvent.html)
    18. [`RTCStatsReport`](RTCStatsReport.html)
    19. [`RTCErrorEvent`](RTCErrorEvent.html)
4.  Properties
    1.  [`Navigator.mediaDevices`](Navigator/mediaDevices.html)
5.  Methods
    1.  [`MediaDevices.getUserMedia()`](MediaDevices/getUserMedia.html)
6.  Events
    1.  [`RTCDTMFSender`: `tonechange`](RTCDTMFSender/tonechange_event.html)
    2.  [`RTCDataChannel`: `bufferedamountlow`](RTCDataChannel/bufferedamountlow_event.html)
    3.  [`RTCDataChannel`: `close`](RTCDataChannel/close_event.html)
    4.  [`RTCDataChannel`: `closing`](RTCDataChannel/closing_event.html)
    5.  [`RTCDataChannel`: `error`](RTCDataChannel/error_event.html)
    6.  [`RTCDataChannel`: `message`](RTCDataChannel/message_event.html)
    7.  [`RTCDataChannel`: `open`](RTCDataChannel/open_event.html)
    8.  [`RTCDtlsTransport`: `error`](RTCDtlsTransport/error_event.html)
    9.  [`RTCDtlsTransport`: `statechange`](RTCDtlsTransport/statechange_event.html)
    10. [`RTCIceTransport`: `error`](RTCIceTransport/error_event.html)
    11. [`RTCIceTransport`: `gatheringstatechange`](RTCIceTransport/gatheringstatechange_event.html)
    12. [`RTCIceTransport`: `selectedcandidatepairchange`](RTCIceTransport/selectedcandidatepairchange_event.html)
    13. [`RTCIceTransport`: `statechange`](RTCIceTransport/statechange_event.html)
    14. [`RTCPeerConnection`: `connectionstatechange`](RTCPeerConnection/connectionstatechange_event.html)
    15. [`RTCPeerConnection`: `datachannel`](RTCPeerConnection/datachannel_event.html)
    16. [`RTCPeerConnection`: `icecandidate`](RTCPeerConnection/icecandidate_event.html)
    17. [`RTCPeerConnection`: `icecandidateerror`](RTCPeerConnection/icecandidateerror_event.html)
    18. [`RTCPeerConnection`: `iceconnectionstatechange`](RTCPeerConnection/iceconnectionstatechange_event.html)
    19. [`RTCPeerConnection`: `icegatheringstatechange`](RTCPeerConnection/icegatheringstatechange_event.html)
    20. [`RTCPeerConnection`: `negotiationneeded`](RTCPeerConnection/negotiationneeded_event.html)
    21. [`RTCPeerConnection`: `signalingstatechange`](RTCPeerConnection/signalingstatechange_event.html)
    22. [`RTCPeerConnection`: `track`](RTCPeerConnection/track_event.html)
    23. [`RTCSctpTransport`: `error`](RTCSctpTransport/error_event.html)

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
