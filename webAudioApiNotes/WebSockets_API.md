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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API" class="breadcrumb-current-page"><span data-property="name">The WebSocket API (WebSockets)</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Interfaces](#interfaces)
-   [Guides](#guides)
-   [Tools](#tools)
-   [Related Topics](#related_topics)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

The WebSocket API (WebSockets)
==============================

The **WebSocket API** is an advanced technology that makes it possible to open a two-way interactive communication session between the user's browser and a server. With this API, you can send messages to a server and receive event-driven responses without having to poll the server for a reply.

**Note:** While a WebSocket connection is functionally somewhat similar to standard Unix-style sockets, they are not related.

[Interfaces](#interfaces "Permalink to Interfaces")
---------------------------------------------------

[`WebSocket`](https://developer.mozilla.org/en-US/docs/Web/API/WebSocket)  
The primary interface for connecting to a WebSocket server and then sending and receiving data on the connection.

`CloseEvent`  
The event sent by the WebSocket object when the connection closes.

[`MessageEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MessageEvent)  
The event sent by the WebSocket object when a message is received from the server.

[Guides](#guides "Permalink to Guides")
---------------------------------------

-   [Writing WebSocket client applications](https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API/Writing_WebSocket_client_applications)
-   [Writing WebSocket servers](https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API/Writing_WebSocket_servers)
-   [Writing a WebSocket server in C\#](https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API/Writing_WebSocket_server)
-   [Writing a WebSocket server in Java](https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API/Writing_a_WebSocket_server_in_Java)

[Tools](#tools "Permalink to Tools")
------------------------------------

-   <a href="https://www.asyncapi.com/" class="external">AsyncAPI</a>: A specification for describing event-driven architectures like WebSocket. You can use it to describe WebSocket-based APIs just as you would describe REST APIs with the OpenAPI specification. Learn <a href="https://www.asyncapi.com/blog/websocket-part1" class="external">why you should consider using AsyncAPI with WebSocket</a> and <a href="https://www.asyncapi.com/blog/websocket-part2" class="external">how to do so</a>.
-   <a href="https://hacks.mozilla.org/2017/06/introducing-humblenet-a-cross-platform-networking-library-that-works-in-the-browser/" class="external">HumbleNet</a>: A cross-platform networking library that works in the browser. It consists of a C wrapper around WebSockets and WebRTC that abstracts away cross-browser differences, facilitating the creation of multi-user networking functionality for games and other apps.
-   <a href="https://github.com/uWebSockets/uWebSockets" class="external">µWebSockets</a>: Highly scalable WebSocket server and client implementation for <a href="https://isocpp.org/" class="external">C++11</a> and <a href="https://nodejs.org/" class="external">Node.js</a>.
-   <a href="https://github.com/ClusterWS/ClusterWS" class="external">ClusterWS</a>:  Lightweight, fast and powerful framework for building scalable WebSocket applications in <a href="https://nodejs.org/" class="external">Node.js</a>.
-   <a href="https://github.com/ClusterWS/cWS" class="external">CWS</a>: Fast C++ WebSocket implementation for Node.js (uWebSockets v0.14 fork)
-   <a href="https://socket.io/" class="external">Socket.IO</a>: A long polling/WebSocket based third party transfer protocol for <a href="https://nodejs.org/" class="external">Node.js</a>.
-   <a href="https://socketcluster.io/" class="external">SocketCluster</a>: A pub/sub WebSocket framework for <a href="https://nodejs.org/" class="external">Node.js</a> with a focus on scalability.
-   <a href="https://github.com/Worlize/WebSocket-Node" class="link-https external">WebSocket-Node</a>: A WebSocket server API implementation for <a href="https://nodejs.org/" class="external">Node.js</a>.
-   <a href="https://www.totaljs.com/" class="external">Total.js</a>: Web application framework for <a href="https://www.nodejs.org/" class="external">Node.js</a> (Example: <a href="https://github.com/totaljs/examples/tree/master/websocket" class="external">WebSocket chat</a>)
-   <a href="https://www.npmjs.com/package/faye-websocket" class="external">Faye</a>: A [`WebSocket`](https://developer.mozilla.org/en-US/docs/Web/API/WebSocket) (two-ways connections) and [EventSource](https://developer.mozilla.org/en-US/docs/Web/API/EventSource) (one-way connections) for <a href="https://nodejs.org/" class="external">Node.js</a> Server and Client.
-   <a href="https://signalr.net/" class="external">SignalR</a>: SignalR will use WebSockets under the covers when it's available, and gracefully fallback to other techniques and technologies when it isn't, while your application code stays the same.
-   <a href="https://caddyserver.com/" class="external">Caddy</a>: A web server capable of proxying arbitrary commands (stdin/stdout) as a websocket.
-   <a href="https://github.com/websockets/ws" class="external">ws</a>: a popular WebSocket client & server library for <a href="https://nodejs.org/" class="external">Node.js</a>.
-   <a href="https://github.com/bigstepinc/jsonrpc-bidirectional" class="external">jsonrpc-bidirectional</a>: Asynchronous RPC which, on a single connection, may have functions exported on the server and, and the same time, on the client (client may call server, server may also call client).
-   <a href="https://github.com/ninenines/cowboy" class="external">cowboy</a>: Cowboy is a small, fast and modern HTTP server for Erlang/OTP with WebSocket support.
-   <a href="https://websocketking.com/" class="external">WebSocket King</a>: A client tool to help develop, test and work with WebSocket servers.
-   <a href="https://github.com/napengam/phpWebSocketServer" class="external">PHP WebSocket Server</a>: Server written in PHP to handle connections via websocksets wss:// or ws://and normal sockets over ssl:// ,tcp://
-   <a href="https://channels.readthedocs.io/en/stable/index.html" class="external">Channels</a>: Django library that adds support for WebSockets (and other protocols that require long running asynchronous connections).
-   <a href="https://flask-socketio.readthedocs.io/en/latest/" class="external">Flask-SocketIO</a>: gives Flask applications access to low latency bi-directional communications between the clients and the server.
-   <a href="https://pkg.go.dev/github.com/gorilla/websocket" class="external">Gorilla WebSocket</a>: Gorilla WebSocket is a <a href="https://golang.org/" class="external">Go</a> implementation of the WebSocket protocol.

[Related Topics](#related_topics "Permalink to Related Topics")
---------------------------------------------------------------

-   [AJAX](https://developer.mozilla.org/en-US/docs/Web/Guide/AJAX)
-   [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript)

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comments</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/web-sockets.html" class="external">HTML Living Standard<br />
<span class="small">The definition of 'WebSocket API' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/websockets/" class="external">WebSockets</a></td><td><span class="spec-CR">Candidate Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc6455" class="external">RFC 6455: The WebSocket Protocol</a></td><td><span class="spec-RFC">IETF RFC</span></td><td></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   <a href="https://datatracker.ietf.org/doc/html/rfc6455" class="external">RFC 6455 — The WebSocket Protocol</a>
-   <a href="https://www.w3.org/TR/websockets/" class="external">WebSocket API Specification</a>
-   [Server-Sent Events](https://developer.mozilla.org/en-US/docs/Web/API/Server-sent_events)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/websockets_api/index.html "Folder: en-us/web/api/websockets_api (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWebSockets_API%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fwebsockets_api%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWebSockets_API%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fwebsockets_api%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F133eb9e813d8aebe5dd6f25b2825d14f054d7f9a%0A*+Document+last+modified%3A+2021-05-25T15%3A44%3A53.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22The+WebSocket+API+%28WebSockets%29%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 25, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API/contributors.txt)

Change your languageSelect your preferred language English (US)DeutschEspañolFrançais日本語한국어PolskiPortuguês (do Brasil)Русский中文 (简体)正體中文 (繁體)

Change language

#### Related Topics

1.  **[Websockets API](https://developer.mozilla.org/en-US/docs/Web/API/Websockets_API)**
2.  Guides
    1.  [Writing WebSocket client applications](https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API/Writing_WebSocket_client_applications)
    2.  [Writing WebSocket servers](https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API/Writing_WebSocket_servers)
    3.  [Writing a WebSocket server in C\#](https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API/Writing_WebSocket_server)
    4.  [Writing a WebSocket server in Java](https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API/Writing_a_WebSocket_server_in_Java)
3.  Interfaces
    1.  [`WebSocket`](https://developer.mozilla.org/en-US/docs/Web/API/WebSocket)
    2.  [`CloseEvent`](https://developer.mozilla.org/en-US/docs/Web/API/CloseEvent)
    3.  [`MessageEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MessageEvent)

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
