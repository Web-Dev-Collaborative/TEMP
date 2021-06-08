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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API" class="breadcrumb-penultimate"><span data-property="name">Web Workers API</span></a>
4.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Functions_and_classes_available_to_workers" class="breadcrumb-current-page"><span data-property="name">Functions and classes available to Web Workers</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Worker Contexts & Functions](#worker_contexts_functions)
-   [Web APIs available in workers](#web_apis_available_in_workers)
-   [See also](#see_also)

Functions and classes available to Web Workers
==============================================

In addition to the standard [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript) set of functions (such as [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String), [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array), [`Object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object), [`JSON`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON), etc), there are a variety of functions available from the DOM to workers. This article provides a list of those.

[Worker Contexts & Functions](#worker_contexts_functions "Permalink to Worker Contexts & Functions")
----------------------------------------------------------------------------------------------------

**Workers run in a different global context than the current window!** While  [`Window`](https://developer.mozilla.org/en-US/docs/Web/API/Window) is not directly available to workers, many of the same methods are defined in a shared mixin ([`WindowOrWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope)), and made available to workers through their own [`WorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope)-derived contexts: 

-   [`DedicatedWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/DedicatedWorkerGlobalScope) for dedicated workers
-   [`SharedWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorkerGlobalScope) for shared workers
-   [`ServiceWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope) for [service workers](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API)

Some of the functions that are common to all workers and to the main thread (from [`WindowOrWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope)) are: [`atob()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/atob "atob()"), [`btoa()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/btoa "btoa()"), [`clearInterval()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/clearInterval "clearInterval()"), [`clearTimeout()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/clearTimeout "clearTimeout()"),[`dump()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/dump "dump()") , [`setInterval()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setInterval "setInterval()"), [`setTimeout()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setTimeout "setTimeout()").

The following functions are **only** available to workers:

-   [`WorkerGlobalScope.importScripts()`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/importScripts "WorkerGlobalScope.importScripts()") (all workers), 
-   [`close()`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/close "close()")
    (dedicated and shared workers only), 
-   [`DedicatedWorkerGlobalScope.postMessage`](https://developer.mozilla.org/en-US/docs/Web/API/DedicatedWorkerGlobalScope/postMessage) (dedicated workers only).

[Web APIs available in workers](#web_apis_available_in_workers "Permalink to Web APIs available in workers")
------------------------------------------------------------------------------------------------------------

Note that if a listed API is supported by a platform in a particular version, then it can generally be assumed to work in web workers.

The following Web APIs are available to workers: [`Broadcast Channel API`](https://developer.mozilla.org/en-US/docs/Web/API/Broadcast_Channel_API "Broadcast Channel API"), [`Cache API`](https://developer.mozilla.org/en-US/docs/Web/API/Cache "Cache API"),[`Channel Messaging API`](https://developer.mozilla.org/en-US/docs/Web/API/Channel_Messaging_API "Channel Messaging API"),[`Console API`](https://developer.mozilla.org/en-US/docs/Web/API/Console "Console API"), [`Crypto`](https://developer.mozilla.org/en-US/docs/Web/API/Crypto), [`CustomEvent`](https://developer.mozilla.org/en-US/docs/Web/API/CustomEvent), <span class="page-not-created">`Data Store`</span> (Firefox only), <span class="page-not-created">`DOMRequest`</span> and <span class="page-not-created">`DOMCursor`</span>, [`Fetch`](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API "Fetch"), [`FileReader`](https://developer.mozilla.org/en-US/docs/Web/API/FileReader), [`FileReaderSync`](https://developer.mozilla.org/en-US/docs/Web/API/FileReaderSync) (only works in workers!), [`FormData`](https://developer.mozilla.org/en-US/docs/Web/API/FormData), [`ImageData`](https://developer.mozilla.org/en-US/docs/Web/API/ImageData), [`IndexedDB`](https://developer.mozilla.org/en-US/docs/Web/API/IndexedDB_API "IndexedDB"), [Network Information API](https://developer.mozilla.org/en-US/docs/Web/API/Network_Information_API), [`Notifications`](https://developer.mozilla.org/en-US/docs/Web/API/Notifications_API "Notifications"), [`Performance`](https://developer.mozilla.org/en-US/docs/Web/API/Performance), [`PerformanceEntry`](https://developer.mozilla.org/en-US/docs/Web/API/PerformanceEntry), [`PerformanceMeasure`](https://developer.mozilla.org/en-US/docs/Web/API/PerformanceMeasure), [`PerformanceMark`](https://developer.mozilla.org/en-US/docs/Web/API/PerformanceMark), [`PerformanceObserver`](https://developer.mozilla.org/en-US/docs/Web/API/PerformanceObserver), [`PerformanceResourceTiming`](https://developer.mozilla.org/en-US/docs/Web/API/PerformanceResourceTiming), [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise), [Server-sent events](https://developer.mozilla.org/en-US/docs/Web/API/Server-sent_events), [`ServiceWorkerRegistration`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerRegistration), [`TextEncoder`](https://developer.mozilla.org/en-US/docs/Web/API/TextEncoder) and [`TextDecoder`](https://developer.mozilla.org/en-US/docs/Web/API/TextDecoder), [`URL`](https://developer.mozilla.org/en-US/docs/Web/API/URL), [WebGL](https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API) with [`OffscreenCanvas`](https://developer.mozilla.org/en-US/docs/Web/API/OffscreenCanvas) (enabled behind a feature preference setting `gfx.offscreencanvas.enabled`), [`WebSocket`](https://developer.mozilla.org/en-US/docs/Web/API/WebSocket), [`XMLHttpRequest`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest).

Workers can also spawn other workers, so these APIs are also available: [`Worker`](https://developer.mozilla.org/en-US/docs/Web/API/Worker), [`WorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope), [`WorkerLocation`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerLocation), [`WorkerNavigator`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerNavigator).

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Using web workers](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Using_web_workers)
-   [`Worker`](https://developer.mozilla.org/en-US/docs/Web/API/Worker)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/web_workers_api/functions_and_classes_available_to_workers/index.html "Folder: en-us/web/api/web_workers_api/functions_and_classes_available_to_workers (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWeb_Workers_API%2FFunctions_and_classes_available_to_workers%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fweb_workers_api%2Ffunctions_and_classes_available_to_workers%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWeb_Workers_API%2FFunctions_and_classes_available_to_workers%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fweb_workers_api%2Ffunctions_and_classes_available_to_workers%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fdae501306b38df26aeace4b708ef4e1a6fa092f9%0A*+Document+last+modified%3A+2021-05-06T22%3A47%3A48.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22Functions+and+classes+available+to+Web+Workers%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 6, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Functions_and_classes_available_to_workers/contributors.txt)

Change your languageSelect your preferred language English (US)Français日本語Русский中文 (简体)

Change language

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
