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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/WorkerLocation" class="breadcrumb-current-page"><span data-property="name">WorkerLocation</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Properties](#properties)
-   [Methods](#methods)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

WorkerLocation
==============

The **`WorkerLocation`** interface defines the absolute location of the script executed by the [`Worker`](https://developer.mozilla.org/en-US/docs/Web/API/Worker). Such an object is initialized for each worker and is available via the [`WorkerGlobalScope.location`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/location) property obtained by calling `self.location`.

This interface is only visible from inside a JavaScript script executed in the context of a Web worker.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

[`WorkerLocation.href`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerLocation/href) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString) containing the serialized [`URL`](https://developer.mozilla.org/en-US/docs/Web/API/URL) for the worker’s location.

[`WorkerLocation.protocol`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerLocation/protocol) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the [`protocol`](https://developer.mozilla.org/en-US/docs/Web/API/URL/protocol "protocol") part of the worker’s location.

[`WorkerLocation.host`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerLocation/host) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the [`host`](https://developer.mozilla.org/en-US/docs/Web/API/URL/host "host") part of the worker’s location.

[`WorkerLocation.hostname`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerLocation/hostname) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the [`hostname`](https://developer.mozilla.org/en-US/docs/Web/API/URL/hostname "hostname") part of the worker’s location.

[`WorkerLocation.origin`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerLocation/origin) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the worker’s [`origin`](https://developer.mozilla.org/en-US/docs/Web/API/URL/origin "origin").

[`WorkerLocation.port`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerLocation/port) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the [`port`](https://developer.mozilla.org/en-US/docs/Web/API/URL/port "port") part of the worker’s location.

[`WorkerLocation.pathname`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerLocation/pathname) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the [`pathname`](https://developer.mozilla.org/en-US/docs/Web/API/URL/pathname "pathname") part of the worker’s location.

[`WorkerLocation.search`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerLocation/search) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the [`search`](https://developer.mozilla.org/en-US/docs/Web/API/URL/search "search") part of the worker’s location.

[`WorkerLocation.hash`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerLocation/hash) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the [`hash`](https://developer.mozilla.org/en-US/docs/Web/API/URL/hash "hash") part of the worker’s location.

[Methods](#methods "Permalink to Methods")
------------------------------------------

[`WorkerLocation.toString()`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerLocation/toString)  
Returns a [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString) containing the serialized [`URL`](https://developer.mozilla.org/en-US/docs/Web/API/URL) for the worker’s location. It is a synonym for [`WorkerLocation.href`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerLocation/href).

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#workerlocation" class="external">HTML Living Standard<br />
<span class="small">The definition of 'WorkerLocation' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   Other Worker-related interfaces: [`Worker`](https://developer.mozilla.org/en-US/docs/Web/API/Worker), [`WorkerNavigator`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerNavigator), and [`WorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope).
-   [Using web workers](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Using_web_workers)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/workerlocation/index.html "Folder: en-us/web/api/workerlocation (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWorkerLocation%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fworkerlocation%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWorkerLocation%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fworkerlocation%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F94c536f9b3a50303a85e7963a4ff4958d1aec382%0A*+Document+last+modified%3A+2021-05-31T17%3A13%3A02.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22WorkerLocation%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/WorkerLocation/contributors.txt)

Change your languageSelect your preferred language English (US)Français日本語

Change language

#### Related Topics

1.  **[Web Workers API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API)**
2.  **[`WorkerLocation`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerLocation)**
3.  Properties
    1.  [`hash`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerLocation/hash)
    2.  [`host`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerLocation/host)
    3.  [`hostname`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerLocation/hostname)
    4.  [`href`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerLocation/href)
    5.  [`origin`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerLocation/origin)
    6.  [`pathname`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerLocation/pathname)
    7.  [`port`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerLocation/port)
    8.  [`protocol`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerLocation/protocol)
    9.  [`search`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerLocation/search)
4.  Methods
    1.  [`toString()`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerLocation/toString)
5.  Related pages for Web Workers API
    1.  [`AbstractWorker`](https://developer.mozilla.org/en-US/docs/Web/API/AbstractWorker)
    2.  [`ChromeWorker`](https://developer.mozilla.org/en-US/docs/Web/API/ChromeWorker)
    3.  [`DedicatedWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/DedicatedWorkerGlobalScope)
    4.  [`ServiceWorker`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorker)
    5.  [`SharedWorker`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorker)
    6.  [`SharedWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorkerGlobalScope)
    7.  [`Worker`](https://developer.mozilla.org/en-US/docs/Web/API/Worker)
    8.  [`WorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope)
    9.  [`WorkerNavigator`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerNavigator)

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
