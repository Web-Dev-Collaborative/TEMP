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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope" class="breadcrumb-current-page"><span data-property="name">WorkerGlobalScope</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Properties](#properties)
-   [Events](#events)
-   [Methods](#methods)
-   [Example](#example)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

WorkerGlobalScope
=================

The `WorkerGlobalScope` interface of the [Web Workers API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API) is an interface representing the scope of any worker. Workers have no browsing context; this scope contains the information usually conveyed by [`Window`](https://developer.mozilla.org/en-US/docs/Web/API/Window) objects — in this case event handlers, the console or the associated [`WorkerNavigator`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerNavigator) object. Each `WorkerGlobalScope` has its own event loop.

This interface is usually specialized by each worker type: [`DedicatedWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/DedicatedWorkerGlobalScope) for dedicated workers, [`SharedWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorkerGlobalScope) for shared workers, and [`ServiceWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope) for [ServiceWorker](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API). The `self` property returns the specialized scope for each context.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

*This interface inherits properties from the [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget) interface and [`WindowOrWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope) and [`WindowEventHandlers`](https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers) mixins.*

### [Standard properties](#standard_properties "Permalink to Standard properties")

[`WorkerGlobalScope.navigator`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/navigator) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the [`WorkerNavigator`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerNavigator) associated with the worker. It is a specific navigator object, mostly a subset of the [`Navigator`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator) for browsing scopes, but adapted to workers.

[`WorkerGlobalScope.self`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/self) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a reference to the `WorkerGlobalScope` itself. Most of the time it is a specific scope like [`DedicatedWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/DedicatedWorkerGlobalScope),  [`SharedWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorkerGlobalScope) or [`ServiceWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope).

[`WorkerGlobalScope.location`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/location) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the [`WorkerLocation`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerLocation) associated with the worker. It is a specific location object, mostly a subset of the [`Location`](https://developer.mozilla.org/en-US/docs/Web/API/Location) for browsing scopes, but adapted to workers.

### [Non-standard properties](#non-standard_properties "Permalink to Non-standard properties")

[`WorkerGlobalScope.performance`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/performance) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
Returns the [`Performance`](https://developer.mozilla.org/en-US/docs/Web/API/Performance) associated with the worker. It is a regular performance object, except that only a subset of its property and methods are available to workers.

[`WorkerGlobalScope.console`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/console) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
Returns the [`Console`](https://developer.mozilla.org/en-US/docs/Web/API/Console) associated with the worker.

### [Properties implemented from elsewhere](#properties_implemented_from_elsewhere "Permalink to Properties implemented from elsewhere")

[`WindowOrWorkerGlobalScope.caches`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/caches) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the [`CacheStorage`](https://developer.mozilla.org/en-US/docs/Web/API/CacheStorage) object associated with the current context. This object enables functionality such as storing assets for offline use, and generating custom responses to requests.

[`WindowOrWorkerGlobalScope.indexedDB`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/indexedDB) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Provides a mechanism for applications to asynchronously access capabilities of indexed databases; returns an [`IDBFactory`](https://developer.mozilla.org/en-US/docs/Web/API/IDBFactory) object.

[`WindowOrWorkerGlobalScope.isSecureContext`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/isSecureContext) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a boolean indicating whether the current context is secure (`true`) or not (`false`).

[`WindowOrWorkerGlobalScope.origin`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/origin) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the global object's origin, serialized as a string. (This does not yet appear to be implemented in any browser.)

[Events](#events "Permalink to Events")
---------------------------------------

`error`  
Fired when an error occurred.  
Also available via the [`WorkerGlobalScope.onerror`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/onerror) property.

`offline`  
Fired when the browser has lost access to the network and the value of `navigator.onLine` switched to `false`.  
Also available via the [`WorkerGlobalScope.onoffline`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/onoffline) property.

`online`  
Fired when the browser has gained access to the network and the value of `navigator.onLine` switched to `true`.  
Also available via the [`WorkerGlobalScope.ononline`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/ononline) property.

`languagechange`  
Fired at the global/worker scope object when the user's preferred languages change.  
Also available via the [`WorkerGlobalScope.onlanguagechange`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/onlanguagechange) property.

`close`   
Is an `event handler` representing the code to be called when the `close` event is raised.  
Also available via the [`WorkerGlobalScope.onclose`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/onclose) property.

`rejectionhandled`   
An event handler for handled [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise "The Promise object is used for deferred and asynchronous computations. A Promise represents an operation that hasn't completed yet, but is expected in the future.") rejection events.  
Also available via the <span class="page-not-created">`WorkerGlobalScope.onrejectionhandled`</span> property.

`unhandledrejection`   
An event handler for unhandled [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise "The Promise object is used for deferred and asynchronous computations. A Promise represents an operation that hasn't completed yet, but is expected in the future.") rejection events.  
Also available via the <span class="page-not-created">`WorkerGlobalScope.onunhandledrejection`</span> property.

[Methods](#methods "Permalink to Methods")
------------------------------------------

*This interface inherits methods from the [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget) interface and [`WindowOrWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope) and [`WindowEventHandlers`](https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers) mixins.*

### [Standard methods](#standard_methods "Permalink to Standard methods")

[`WorkerGlobalScope.importScripts()`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/importScripts)  
Imports one or more scripts into the worker's scope. You can specify as many as you'd like, separated by commas. For example:` importScripts('foo.js', 'bar.js');`

### [Non-standard methods](#non-standard_methods "Permalink to Non-standard methods")

[`WorkerGlobalScope.dump()`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/dump)   
Allows you to write a message to stdout — i.e. in your terminal. This is the same as Firefox's [`window.dump`](https://developer.mozilla.org/en-US/docs/Web/API/Window/dump), but for workers.

### [Methods implemented from elsewhere](#methods_implemented_from_elsewhere "Permalink to Methods implemented from elsewhere")

[`WindowOrWorkerGlobalScope.atob()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/atob)  
Decodes a string of data which has been encoded using base-64 encoding.

[`WindowOrWorkerGlobalScope.btoa()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/btoa)  
Creates a base-64 encoded ASCII string from a string of binary data.

[`WindowOrWorkerGlobalScope.clearInterval()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/clearInterval)  
Cancels the repeated execution set using [`WindowOrWorkerGlobalScope.setInterval()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setInterval).

[`WindowOrWorkerGlobalScope.clearTimeout()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/clearTimeout)  
Cancels the delayed execution set using [`WindowOrWorkerGlobalScope.setTimeout()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setTimeout).

[`WindowOrWorkerGlobalScope.createImageBitmap()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/createImageBitmap)  
Accepts a variety of different image sources, and returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which resolves to an [`ImageBitmap`](https://developer.mozilla.org/en-US/docs/Web/API/ImageBitmap). Optionally the source is cropped to the rectangle of pixels originating at *(sx, sy)* with width sw, and height sh.

[`WindowOrWorkerGlobalScope.fetch()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/fetch)  
Starts the process of fetching a resource from the network.

[`WindowOrWorkerGlobalScope.setInterval()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setInterval)  
Schedules a function to execute every time a given number of milliseconds elapses.

[`WindowOrWorkerGlobalScope.setTimeout()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setTimeout)  
Schedules a function to execute in a given amount of time.

### [Deprecated methods](#deprecated_methods "Permalink to Deprecated methods")

[`WorkerGlobalScope.close()`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/close)  
Discards any tasks queued in the `WorkerGlobalScope`'s event loop, effectively closing this particular scope. In newer browser versions, `close()` is available on `DedicatedWorkerGlobalScope` and [`SharedWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorkerGlobalScope/close "SharedWorkerGlobalScope") instead. This change was made to stop `close()` being available on service workers, as it isn't supposed to be used there and always throws an exception when called (see <a href="https://bugzilla.mozilla.org/show_bug.cgi?id=1336043" class="external">bug 1336043</a>).

[Example](#example "Permalink to Example")
------------------------------------------

You won't access `WorkerGlobalScope` directly in your code; however, its properties and methods are inherited by more specific global scopes such as [`DedicatedWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/DedicatedWorkerGlobalScope) and [`SharedWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorkerGlobalScope). For example, you could import another script into the worker and print out the contents of the worker scope's `navigator` object using the following two lines:

    importScripts('foo.js');
    console.log(navigator);

Since the global scope of the worker script is effectively the global scope of the worker you are running ([`DedicatedWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/DedicatedWorkerGlobalScope) or whatever) and all worker global scopes inherit methods, properties, etc. from `WorkerGlobalScope`, you can run lines such as those above without specifying a parent object.

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#workerglobalscope" class="external">HTML Living Standard<br />
<span class="small">The definition of 'WorkerGlobalScope' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   Other global object interface: [`Window`](https://developer.mozilla.org/en-US/docs/Web/API/Window), [`DedicatedWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/DedicatedWorkerGlobalScope), [`SharedWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorkerGlobalScope), , [`ServiceWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope)
-   Other Worker-related interfaces: [`Worker`](https://developer.mozilla.org/en-US/docs/Web/API/Worker), [`WorkerLocation`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerLocation), [`WorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope), and [`ServiceWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope).
-   [Using web workers.](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Using_web_workers)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/workerglobalscope/index.html "Folder: en-us/web/api/workerglobalscope (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWorkerGlobalScope%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fworkerglobalscope%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWorkerGlobalScope%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fworkerglobalscope%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F94c536f9b3a50303a85e7963a4ff4958d1aec382%0A*+Document+last+modified%3A+2021-05-31T17%3A13%3A02.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22WorkerGlobalScope%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/contributors.txt)

Change your languageSelect your preferred language English (US)Français日本語Русский中文 (简体)

Change language

#### Related Topics

1.  **[Web Workers API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API)**
2.  **[`WorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope)**
3.  Properties
    1.  [`caches`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/caches)
    2.  [`console`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/console)
    3.  [`crossOriginIsolated`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/crossOriginIsolated)
    4.  [`indexedDB`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/indexedDB)
    5.  [`isSecureContext`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/isSecureContext)
    6.  [`location`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/location)
    7.  [`navigator`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/navigator)
    8.  [`onclose`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/onclose)
    9.  [`onerror`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/onerror)
    10. [`onlanguagechange`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/onlanguagechange)
    11. [`onoffline`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/onoffline)
    12. [`ononline`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/ononline)
    13. [`origin`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/origin)
    14. [`performance`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/performance)
    15. [`self`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/self)
4.  Methods
    1.  [`atob()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/atob)
    2.  [`btoa()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/btoa)
    3.  [`clearInterval()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/clearInterval)
    4.  [`clearTimeout()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/clearTimeout)
    5.  [`close()`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/close)
    6.  [`createImageBitmap()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/createImageBitmap)
    7.  [`dump()`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/dump)
    8.  [`fetch()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/fetch)
    9.  [`importScripts()`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/importScripts)
    10. [`queueMicrotask()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/queueMicrotask)
    11. [`setInterval()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setInterval)
    12. [`setTimeout()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setTimeout)
5.  Events
    1.  [`languagechange`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/languagechange_event)
6.  Inheritance:
    1.  [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)
7.  Related pages for Web Workers API
    1.  [`AbstractWorker`](https://developer.mozilla.org/en-US/docs/Web/API/AbstractWorker)
    2.  [`ChromeWorker`](https://developer.mozilla.org/en-US/docs/Web/API/ChromeWorker)
    3.  [`DedicatedWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/DedicatedWorkerGlobalScope)
    4.  [`ServiceWorker`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorker)
    5.  [`SharedWorker`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorker)
    6.  [`SharedWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorkerGlobalScope)
    7.  [`Worker`](https://developer.mozilla.org/en-US/docs/Web/API/Worker)
    8.  [`WorkerLocation`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerLocation)
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
