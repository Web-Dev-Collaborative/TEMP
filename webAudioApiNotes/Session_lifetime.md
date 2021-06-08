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
4.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Session_lifetime" class="breadcrumb-current-page"><span data-property="name">Lifetime of a WebRTC session</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Establishing the connection](#establishing_the_connection)
-   [ICE restart](#ice_restart)
-   [Transmission](#transmission)
-   [Reception](#reception)

Lifetime of a WebRTC session
============================

#### Draft

This page is not complete.

<span class="seoSummary">WebRTC lets you build peer-to-peer communication of arbitrary data, audio, or video—or any combination thereof—into a browser application. In this article, we'll look at the lifetime of a WebRTC session, from establishing the connection all the way through closing the connection when it's no longer needed.</span>

This article doesn't get into details of the actual APIs involved in establishing and handling a WebRTC connection; it reviews the process in general with some information about why each step is required. See [Signaling and video calling](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Signaling_and_video_calling) for an actual example with a step-by-step explanation of what the code does.

This page is currently under construction, and some of the content will move to other pages as the WebRTC guide material is built out. Pardon our dust!

[Establishing the connection](#establishing_the_connection "Permalink to Establishing the connection")
------------------------------------------------------------------------------------------------------

The Internet is big. Really big. It’s so big that years ago, smart people saw how big it was, how fast it was growing, and the <a href="https://en.wikipedia.org/wiki/IPv4_address_exhaustion" class="external" title="limitations">limitations</a> of the 32-bit IP addressing system, and realized that something had to be done before we ran out of addresses to use, so they started working on designing a new 64-bit addressing system. But they realized that it would take longer to complete the transition than 32-bit addresses would last, so other smart people came up with a way to let multiple computers share the same 32-bit IP address. Network Address Translation ([NAT](https://developer.mozilla.org/en-US/docs/Glossary/NAT)) is a standard which supports this address sharing by handling routing of data inbound and outbound to and from devices on a LAN, all of which are sharing a single WAN (global) IP address.

The problem for users is that each individual computer on the Internet no longer necessarily has a unique IP address, and, in fact, each device’s IP address may change not only if they move from one network to another, but if their network’s address is changed by [NAT](https://developer.mozilla.org/en-US/docs/Glossary/NAT) and/or <a href="https://en.wikipedia.org/wiki/DHCP" class="external" title="DHCP">DHCP</a>. For developers trying to do peer-to-peer networking, this introduces a conundrum: without a unique identifier for every user device, it’s not possible to instantly and automatically know how to connect to a specific device on the Internet. Even though you know who you want to talk to, you don’t necessarily know how to reach them or even what their address is.

This is like trying to mail a package to your friend Michelle by labeling it “Michelle” and dropping it in a mailbox when you don't know her address. You need to look up her address and include it on the package, or she'll wind up wondering why you forgot her birthday again.

This is where signaling comes in.

### [Signaling](#signaling "Permalink to Signaling")

Signaling is the process of sending control information between two devices to determine the communication protocols, channels, media codecs and formats, and method of data transfer, as well as any required routing information. The most important thing to know about the signaling process for WebRTC: **it is not defined in the specification**.

Why, you may wonder, is something fundamental to the process of establishing a WebRTC connection left out of the specification? The answer is simple: since the two devices have no way to directly contact each other, and the specification can’t predict every possible use case for WebRTC, it makes more sense to let the developer select an appropriate networking technology and messaging protocol.

In particular, if a developer already has a method in place for connecting two devices, it doesn’t make sense for them to have to use another one, defined by the specification, just for WebRTC. Since WebRTC doesn’t live in a vacuum, there is likely other connectivity in play, so it makes sense to avoid having to add additional connection channels for signaling if an existing one can be used.

In order to exchange signaling information, you can choose to send JSON objects back and forth over a WebSocket connection, or you could use XMPP or SIP over an appropriate channel, or you could use [`XMLHttpRequest`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest) over [HTTPS](https://developer.mozilla.org/en-US/docs/Glossary/https) with polling, or any other combination of technologies you can come up with. You could even use email as the signaling channel.

It’s also worth noting that the channel for performing signaling doesn’t even need to be over the network. One peer can output a data object that can be printed out, physically carried (on foot or by carrier pigeon) to another device, entered into that device, and a response then output by that device to be returned on foot, and so forth, until the WebRTC peer connection is open. It'd be very high latency but it could be done.

#### Information exchanged during signaling

There are three basic types of information that need to be exchanged during signaling:

-   Control messages used to set up, open, and close the communication channel, and to handle errors.
-   Information needed in order to set up the connection: the IP addressing and port information needed for the peers to be able to talk to one another.
-   Media capability negotiation: what codecs and media data formats can the peers understand? These need to be agreed upon before the WebRTC session can begin.

Only once signaling has been successfully completed can the true process of opening the WebRTC peer connection begin.

It's worth noting that the signaling server does not actually need to understand or do anything with the data being exchanged through it by the two peers during signaling. The signaling server is, in essence, a relay: a common point which both sides connect to knowing that their signaling data can be transferred through it. The server doesn't need to react to this information in any way.

#### The signaling process

There's a sequence of things that have to happen in order to make it possible to begin a WebRTC session:

1.  Each peer creates an [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection) object representing their end of the WebRTC session.
2.  Each peer establishes a handler for `icecandidate` events, which handles sending those candidates to the other peer over the signaling channel.
3.  Each peer establishes a handler for `track` event, which is received when the remote peer adds a track to the stream. This code should connect the tracks to its consumer, such as a [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element.
4.  The caller creates and shares with the receiving peer a unique identifier or token of some kind so that the call between them can be identified by the code on the signaling server. The exact contents and form of this identifier is up to you.
5.  Each peer connects to an agreed-upon signaling server, such as a WebSocket server they both know how to exchange messages with.
6.  Each peer tells the signaling server that they want to join the same WebRTC session (identified by the token established in step 4).
7.  ***descriptions, candidates, etc. -- more coming up***

[ICE restart](#ice_restart "Permalink to ICE restart")
------------------------------------------------------

Sometimes, during the lifetime of a WebRTC session, network conditions change. One of the users might transition from a cellular to a WiFi network, or the network might become congested, for example. When this happens, the ICE agent may choose to perform **ICE restart**. This is a process by which the network connection is renegotiated, exactly the same way the initial ICE negotiation is performed, with one exception: media continues to flow across the original network connection until the new one is up and running. Then media shifts to the new network connection and the old one is closed.

**Note:** Different browsers support ICE restart under different sets of conditions. Not all browsers will perform ICE restart due to network congestion, for example.

If you need to change the configuration of the connection in some way (such as changing to a different set of ICE servers), you can do so before restarting ICE by calling [`RTCPeerConnection.setConfiguration()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/setConfiguration) with an updated [`RTCConfiguration`](https://developer.mozilla.org/en-US/docs/Web/API/RTCConfiguration) dictionary before restarting ICE.

To explicitly trigger ICE restart, start the renegotiation process by calling [`RTCPeerConnection.createOffer()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/createOffer), specifying the `iceRestart` option with a value of `true`. Then handle the connection process from then on just like you normally would. This generates new values for the ICE username fragment (ufrag) and password, which will be used by the renegotiation process and the resulting connection.

The answerer side of the connection will automatically begin ICE restart when new values are detected for the ICE ufrag and ICE password.

[Transmission](#transmission "Permalink to Transmission")
---------------------------------------------------------

[Reception](#reception "Permalink to Reception")
------------------------------------------------

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/webrtc_api/session_lifetime/index.html "Folder: en-us/web/api/webrtc_api/session_lifetime (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWebRTC_API%2FSession_lifetime%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fwebrtc_api%2Fsession_lifetime%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWebRTC_API%2FSession_lifetime%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fwebrtc_api%2Fsession_lifetime%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F423ae587ef6e934d8c1313780ff1bd8552b91a8a%0A*+Document+last+modified%3A+2020-12-20T14%3A43%3A36.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22Lifetime+of+a+WebRTC+session%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Dec 20, 2020, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Session_lifetime/contributors.txt)

Change your languageSelect your preferred language English (US)EspañolFrançaisРусский中文 (简体)

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
