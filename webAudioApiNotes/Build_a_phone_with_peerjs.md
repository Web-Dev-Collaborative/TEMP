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
4.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Build_a_phone_with_peerjs" class="breadcrumb-current-page"><span data-property="name">Building an Internet-Connected Phone with PeerJS</span></a>

Building an Internet-Connected Phone with PeerJS
================================================

-   <a href="https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Build_a_phone_with_peerjs/Setup" class="button minimal">Next</a>

One of WebRTC's main issues is that it is pretty complicated to use and develop with — handling the signalling service and knowing when to call the right endpoint can get confusing. But there is some good news; <a href="https://peerjs.com/" class="external">PeerJS</a> is a WebRTC framework that abstracts away all of the ice and signalling logic so that you can focus on the functionality of your application. There are two parts to PeerJS, the client-side framework and the server.

In this series of articles we will create a simple phone application using PeerJS. We’ll be using both the server and the client-side framework, but most of our work will be involved with handling the client-side code.

### [Prerequisites](#prerequisites "Permalink to Prerequisites")

This is an intermediate level tutorial; before attempting it you should already be comfortable with:

-   [Vanilla JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
-   <a href="https://nodejs.org/en/docs/" class="external">Node</a>
-   [Express](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Express_Nodejs)
-   [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML)

Before you get started, you'll want to make sure you've <a href="https://nodejs.org/en/download/" class="external">installed node</a> and <a href="https://classic.yarnpkg.com/en/docs/install" class="external">Yarn</a> (the instructions in later articles assume Yarn, but you can feel free to use <a href="https://docs.npmjs.com/getting-started/" class="external">npm</a> or annother manager if you'd prefer).

#### Note

If you learn better by following step-by-step code, we've also provided this <a href="https://github.com/SamsungInternet/WebPhone/tree/master/tutorial" class="external">tutorial in code</a>, which you can use instead.

### Table of Contents

1.  [Setup](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Build_a_phone_with_peerjs/Setup)
2.  [Connect Peers](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Build_a_phone_with_peerjs/Connect_peers)
    1.  [Get Microphone Permission](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Build_a_phone_with_peerjs/Connect_peers/Get_microphone_permission)
    2.  [Showing and hiding HTML](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Build_a_phone_with_peerjs/Connect_peers/Show_hide_html)
    3.  [Create a Peer Connection](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Build_a_phone_with_peerjs/Connect_peers/Create_a_peer_connection)
    4.  [Creating a Call](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Build_a_phone_with_peerjs/Connect_peers/Creating_a_call)
    5.  [Answer a Call](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Build_a_phone_with_peerjs/Connect_peers/Answer_a_call)
    6.  [End a Call](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Build_a_phone_with_peerjs/Connect_peers/End_a_call)
3.  [Deployment and Further Reading](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Build_a_phone_with_peerjs/Deployment_and_further_reading)

-   <a href="https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Build_a_phone_with_peerjs/Setup" class="button minimal">Next</a>

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/webrtc_api/build_a_phone_with_peerjs/index.html "Folder: en-us/web/api/webrtc_api/build_a_phone_with_peerjs (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWebRTC_API%2FBuild_a_phone_with_peerjs%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fwebrtc_api%2Fbuild_a_phone_with_peerjs%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWebRTC_API%2FBuild_a_phone_with_peerjs%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fwebrtc_api%2Fbuild_a_phone_with_peerjs%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fa76771cc1b0750a64c34b2e81a35925286d897d2%0A*+Document+last+modified%3A+2021-02-16T20%3A33%3A04.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22Building+an+Internet-Connected+Phone+with+PeerJS%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Feb 16, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Build_a_phone_with_peerjs/contributors.txt)

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
