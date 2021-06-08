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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope" class="breadcrumb-current-page"><span data-property="name">WindowOrWorkerGlobalScope</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Properties](#properties_2)
-   [Methods](#methods)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

WindowOrWorkerGlobalScope
=========================

<span class="seoSummary">The **`WindowOrWorkerGlobalScope`** mixin describes several features common to the [`Window`](https://developer.mozilla.org/en-US/docs/Web/API/Window) and [`WorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope) interfaces.</span> Each of these interfaces can, of course, add more features in addition to the ones listed below.

**Note**: `WindowOrWorkerGlobalScope` is a mixin and not an interface; you can't actually create an object of type `WindowOrWorkerGlobalScope`.

[Properties](#properties_2 "Permalink to Properties")
-----------------------------------------------------

These properties are defined on the [`WindowOrWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope) mixin, and implemented by [`Window`](https://developer.mozilla.org/en-US/docs/Web/API/Window) and [`WorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope).

[`WindowOrWorkerGlobalScope.caches`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/caches) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the [`CacheStorage`](https://developer.mozilla.org/en-US/docs/Web/API/CacheStorage) object associated with the current context. This object enables functionality such as storing assets for offline use, and generating custom responses to requests.

[`WindowOrWorkerGlobalScope.crossOriginIsolated`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/crossOriginIsolated) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a boolean value that indicates whether a [`SharedArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/SharedArrayBuffer) can be sent via a [`Window.postMessage()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/postMessage) call.

[`WindowOrWorkerGlobalScope.indexedDB`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/indexedDB) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Provides a mechanism for applications to asynchronously access capabilities of indexed databases; returns an [`IDBFactory`](https://developer.mozilla.org/en-US/docs/Web/API/IDBFactory) object.

[`WindowOrWorkerGlobalScope.isSecureContext`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/isSecureContext) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a boolean indicating whether the current context is secure (`true`) or not (`false`).

[`WindowOrWorkerGlobalScope.origin`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/origin) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the origin of the global scope, serialized as a string.

[Methods](#methods "Permalink to Methods")
------------------------------------------

These methods are defined on the [`WindowOrWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope) mixin, and implemented by [`Window`](https://developer.mozilla.org/en-US/docs/Web/API/Window) and [`WorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope).

[`WindowOrWorkerGlobalScope.atob()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/atob)  
Decodes a string of data which has been encoded using base-64 encoding.

[`WindowOrWorkerGlobalScope.btoa()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/btoa)  
Creates a base-64 encoded ASCII string from a string of binary data.

[`WindowOrWorkerGlobalScope.clearInterval()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/clearInterval)  
Cancels the repeated execution set using [`WindowOrWorkerGlobalScope.setInterval()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setInterval).

[`WindowOrWorkerGlobalScope.clearTimeout()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/clearTimeout)  
Cancels the delayed execution set using [`WindowOrWorkerGlobalScope.setTimeout()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setTimeout).

[`WindowOrWorkerGlobalScope.createImageBitmap()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/createImageBitmap)  
Accepts a variety of different image sources, and returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which resolves to an [`ImageBitmap`](https://developer.mozilla.org/en-US/docs/Web/API/ImageBitmap). Optionally the source is cropped to the rectangle of pixels originating at *(*`sx`, `sy`*)* with width `sw`, and height `sh`.

[`WindowOrWorkerGlobalScope.fetch()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/fetch)  
Starts the process of fetching a resource from the network.

[`WindowOrWorkerGlobalScope.queueMicrotask()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/queueMicrotask)  
Enqueues a microtask—a short function to be executed after execution of the JavaScript code completes and control isn't being returned to a JavaScript caller, but before handling callbacks and other tasks. This lets your code run without interfering with other, possibly higher priority, code, but *before* the browser runtime regains control, potentially depending upon the work you need to complete.

[`WindowOrWorkerGlobalScope.setInterval()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setInterval)  
Schedules a function to execute every time a given number of milliseconds elapses.

[`WindowOrWorkerGlobalScope.setTimeout()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setTimeout)  
Schedules a function to execute in a given amount of time.

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webappapis.html#windoworworkerglobalscope-mixin" class="external">HTML Living Standard<br />
<span class="small">The definition of '<code>WindowOrWorkerGlobalScope</code> mixin' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>This is where the main mixin is defined.</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [`Window`](https://developer.mozilla.org/en-US/docs/Web/API/Window)
-   [`WorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/windoworworkerglobalscope/index.html "Folder: en-us/web/api/windoworworkerglobalscope (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWindowOrWorkerGlobalScope%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fwindoworworkerglobalscope%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWindowOrWorkerGlobalScope%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fwindoworworkerglobalscope%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F94c536f9b3a50303a85e7963a4ff4958d1aec382%0A*+Document+last+modified%3A+2021-05-31T17%3A13%3A02.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22WindowOrWorkerGlobalScope%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/contributors.txt)

Change your languageSelect your preferred language English (US)DeutschEspañolFrançais日本語PolskiPortuguês (do Brasil)Русский中文 (简体)正體中文 (繁體)

Change language

#### Related Topics

1.  **[`WindowOrWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope)**
2.  Properties
    1.  [`caches`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/caches)
    2.  [`crossOriginIsolated`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/crossOriginIsolated)
    3.  [`indexedDB`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/indexedDB)
    4.  [`isSecureContext`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/isSecureContext)
    5.  [`origin`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/origin)
3.  Methods
    1.  [`atob()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/atob)
    2.  [`btoa()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/btoa)
    3.  [`clearInterval()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/clearInterval)
    4.  [`clearTimeout()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/clearTimeout)
    5.  [`createImageBitmap()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/createImageBitmap)
    6.  [`fetch()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/fetch)
    7.  [`queueMicrotask()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/queueMicrotask)
    8.  [`setInterval()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setInterval)
    9.  [`setTimeout()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setTimeout)
4.  Implemented by:
    1.  [`Window`](https://developer.mozilla.org/en-US/docs/Web/API/Window)
    2.  [`WorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope)

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
