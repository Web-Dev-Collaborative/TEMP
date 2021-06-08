;

-   <a href="#content" id="skip-main">Skip to main content</a>
-   <a href="#language" id="skip-language">Select language</a>
-   <a href="#main-q" id="skip-search">Skip to search</a>

<!-- -->

-   Technologies
    -   [Technologies Overview](../../../../external.html?link=https://developer.mozilla.org/en-US/docs/Web)
    -   [HTML](../../../../external.html?link=https://developer.mozilla.org/en-US/docs/Web/HTML)
    -   [CSS](../../../../external.html?link=https://developer.mozilla.org/en-US/docs/Web/CSS)
    -   [JavaScript](../../../../external.html?link=https://developer.mozilla.org/en-US/docs/Web/JavaScript)
    -   [Graphics](../../../../external.html?link=https://developer.mozilla.org/en-US/docs/Web/Guide/Graphics)
    -   [HTTP](../../../../external.html?link=https://developer.mozilla.org/en-US/docs/Web/HTTP)
    -   [APIs / DOM](../../../../external.html?link=https://developer.mozilla.org/en-US/docs/Web/API)
    -   [Browser Extensions](../../../../external.html?link=https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions)
    -   [MathML](../../../../external.html?link=https://developer.mozilla.org/en-US/docs/Web/MathML)
-   References & Guides
    -   [Learn web development](../../../../external.html?link=https://developer.mozilla.org/en-US/docs/Learn)
    -   [Tutorials](../../../../external.html?link=https://developer.mozilla.org/en-US/docs/Web/Tutorials)
    -   [References](../../../../external.html?link=https://developer.mozilla.org/en-US/docs/Web/Reference)
    -   [Developer Guides](../../../../external.html?link=https://developer.mozilla.org/en-US/docs/Web/Guide)
    -   [Accessibility](../../../../external.html?link=https://developer.mozilla.org/en-US/docs/Web/Accessibility)
    -   [Game development](../../../../external.html?link=https://developer.mozilla.org/en-US/docs/Games)
    -   [...more docs](../../../../external.html?link=https://developer.mozilla.org/en-US/docs/Web)
-   Feedback
    -   [Send Feedback](../../../../external.html?link=https://developer.mozilla.org/en-US/docs/MDN/Feedback)
    -   [Get Firefox help 🌐](../../../../external.html?link=https://support.mozilla.org/)
    -   [Get web development help 🌐](../../../../external.html?link=https://stackoverflow.com/)
    -   [Join the MDN community](../../../../external.html?link=https://developer.mozilla.org/en-US/docs/MDN/Community)
    -   [Report a content problem 🌐](../../../../external.html?link=https://github.com/mdn/sprints/issues/new?template=issue-template.md&projects=mdn/sprints/2&labels=user-report&title=/en-US/docs/Glossary/TLS)
    -   [Report an issue 🌐](../../../../external.html?link=https://github.com/mdn/kuma/issues/new/choose)

Search MDN

Open search

1.  <a href="../../../../external.html?link=https://developer.mozilla.org/en-US/docs/Glossary" class="breadcrumb-previous"><span class="pre-text">See </span><span data-property="name">MDN Web Docs Glossary: Definitions of Web-related terms</span></a>
2.  <a href="TLS.html" class="crumb-current-page"><span data-property="name" data-aria-current="page">Transport Layer Security (TLS)</span></a>

English<span class="dropdown-arrow-down" aria-hidden="true">▼</span>

-   [Deutsch](../../../../external.html?link=https://developer.mozilla.org/de/docs/Glossary/TLS "German")
-   [Français](../../../../external.html?link=https://developer.mozilla.org/fr/docs/Glossaire/TLS "French")
-   [日本語](../../../../external.html?link=https://developer.mozilla.org/ja/docs/Glossary/TLS "Japanese")
-   [한국어](../../../../external.html?link=https://developer.mozilla.org/ko/docs/Glossary/TLS "Korean")
-   [Português (do Brasil)](../../../../external.html?link=https://developer.mozilla.org/pt-BR/docs/Glossario/TLS "Portuguese (Brazilian)")
-   [Русский](../../../../external.html?link=https://developer.mozilla.org/ru/docs/Словарь/TLS "Russian")
-   [中文 (简体)](../../../../external.html?link=https://developer.mozilla.org/zh-CN/docs/Glossary/TLS "Chinese (Simplified)")
-   <a href="../../../../external.html?link=https://wiki.developer.mozilla.org/en-US/docs/Glossary/TLS$locales" id="translations-add">Add a translation</a>

**Transport Layer Security (TLS)**, formerly known as <a href="SSL.html" class="glossaryLink" title="Secure Sockets Layer (SSL): Secure Sockets Layer, or SSL, was the old standard security technology for creating an encrypted network link between a server and client, ensuring all data passed is private and secure. The current version of SSL is version 3.0, released by Netscape in 1999, and has been superseded by the Transport Layer Security (TLS) protocol.">Secure Sockets Layer (SSL)</a>, is a <a href="../../../../external.html?link=https://developer.mozilla.org/en-US/docs/Glossary/protocol" class="glossaryLink" title="protocol: A protocol is a system of rules that define how data is exchanged within or between computers. Communications between devices require that the devices agree on the format of the data that is being exchanged. The set of rules that defines a format is called a protocol.">protocol</a> used by applications to communicate securely across a network, preventing tampering with and eavesdropping on email, web browsing, messaging, and other protocols. Both SSL and TLS are client / server protocols that ensure communication privacy by using cryptographic protocols to provide security over a network. When a server and client communicate using TLS, it ensures that no third party can eavesdrop or tamper with any message.

All modern browsers support the TLS protocol, requiring the server to provide a valid <a href="Digital_certificate.html" class="glossaryLink" title="digital certificate: A digital certificate is a data file that binds a publicly known cryptographic key to an organization.">digital certificate</a> confirming its identity in order to establish a secure connection. It is possible for both the client and server to mutually authenticate each other, if both parties provide their own individual digital certificates.

**Note**: TLS 1.0 and 1.1 support will be removed from all major browsers in early 2020; you'll need to make sure your web server supports TLS 1.2 or 1.3 going forward. From version 74 onwards, Firefox will return a <a href="../../../../external.html?link=https://support.mozilla.org/en-US/kb/secure-connection-failed-firefox-did-not-connect" class="external">Secure Connection Failed</a> error when connecting to servers using the older TLS versions (<a href="../../../../external.html?link=https://bugzilla.mozilla.org/show_bug.cgi?id=1606734" class="external" title="FIXED: Disable TLS 1.0 and 1.1 by default">bug 1606734</a>).

#### Metadata

-   **Last modified:** Feb 18, 2020, [by MDN contributors](../../../../external.html?link=https://wiki.developer.mozilla.org/en-US/docs/Glossary/TLS$history)

Related Topics

1.  Specifications
    1.  <a href="../../../../external.html?link=https://tools.ietf.org/html/rfc5246" class="external">RFC 5246</a> (The Transport Layer Security Protocol, Version 1.2)
2.  Wikipedia articles
    1.  <a href="../../../../external.html?link=https://en.wikipedia.org/wiki/Transport%20Layer%20Security" class="external" title="Transport Layer Security">Transport Layer Security</a>
3.  See also
    1.  [Transport Layer Security](../../../../external.html?link=https://developer.mozilla.org/en-US/docs/Web/Security/Transport_Layer_Security)
    2.  <a href="../../../../external.html?link=https://www.owasp.org/index.php/Transport_Layer_Protection_Cheat_Sheet" class="external">OWASP: Transport Layer Protection Cheat Sheet</a>
4.  [Glossary](../../../../external.html?link=https://developer.mozilla.org/en-US/docs/Glossary)
    1.  <a href="../../../../external.html?link=https://developer.mozilla.org/en-US/docs/Glossary/HTTPS" class="glossaryLink" title="HTTPS: HTTPS (HTTP Secure) is an encrypted version of the HTTP protocol. It usually uses SSL or TLS to encrypt all communication between a client and a server. This secure connection allows clients to safely exchange sensitive data with a server, for example for banking activities or online shopping.">HTTPS</a>
    2.  <a href="SSL.html" class="glossaryLink" title="SSL: Secure Sockets Layer, or SSL, was the old standard security technology for creating an encrypted network link between a server and client, ensuring all data passed is private and secure. The current version of SSL is version 3.0, released by Netscape in 1999, and has been superseded by the Transport Layer Security (TLS) protocol.">SSL</a>

Learn the best of web development
---------------------------------

Get the latest and greatest from MDN delivered straight to your inbox.

The newsletter is offered in English only at the moment.

E-mail

I’m okay with Mozilla handling my info as explained in this [Privacy Policy](../../../../external.html?link=https://www.mozilla.org/privacy/).

Sign up now

Hide Newsletter Sign-up

<a href="../../../../external.html?link=https://developer.mozilla.org/en-US/" class="nav-footer-logo">MDN Web Docs</a>

-   [Web Technologies](../../../../external.html?link=https://developer.mozilla.org/en-US/docs/Web)
-   [Learn Web Development](../../../../external.html?link=https://developer.mozilla.org/en-US/docs/Learn)
-   [About MDN](../../../../external.html?link=https://developer.mozilla.org/en-US/docs/MDN/About)
-   [Feedback](../../../../external.html?link=https://developer.mozilla.org/en-US/docs/MDN/Feedback)

<!-- -->

-   [About](../../../../external.html?link=https://www.mozilla.org/about/)
-   [MDN Web Docs Store](../../../../external.html?link=https://shop.spreadshirt.com/mdn-store/)
-   [Contact Us](../../../../external.html?link=https://www.mozilla.org/contact/)
-   [Firefox](../../../../external.html?link=https://www.mozilla.org/firefox/?utm_source=developer.mozilla.org&utm_campaign=footer&utm_medium=referral)

#### MDN

-   -   

#### Mozilla

-   -   

© 2005-2020 Mozilla and individual contributors. Content is available under [these licenses](../../../../external.html?link=https://developer.mozilla.org/docs/MDN/About#Copyrights_and_licenses).

-   [Terms](../../../../external.html?link=https://www.mozilla.org/about/legal/terms/mozilla)
-   [Privacy](../../../../external.html?link=https://www.mozilla.org/privacy/websites/)
-   [Cookies](../../../../external.html?link=https://www.mozilla.org/privacy/websites/#cookies)

Sign In
-------

Sign in to enjoy the benefits of an MDN account. If you haven’t already created an account, you will be prompted to do so after signing in.

<a href="../../../../external.html?link=https://developer.mozilla.org/users/github/login/?next=%2Fen-US%2Fdocs%2FGlossary%2FTLS" class="github-auth">Sign in with Github</a> <a href="../../../../external.html?link=https://developer.mozilla.org/users/google/login/?next=%2Fen-US%2Fdocs%2FGlossary%2FTLS" class="google-auth">Sign in with Google</a>

Close modal
