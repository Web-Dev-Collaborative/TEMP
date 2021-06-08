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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/SharedWorkerGlobalScope" class="breadcrumb-current-page"><span data-property="name">SharedWorkerGlobalScope</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Properties](#properties)
-   [Methods](#methods)
-   [Events](#events)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

SharedWorkerGlobalScope
=======================

The **`SharedWorkerGlobalScope`** object (the [`SharedWorker`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorker) global scope) is accessible through the [`self`](https://developer.mozilla.org/en-US/docs/Web/API/Window/self "self") keyword. Some additional global functions, namespaces objects, and constructors, not typically associated with the worker global scope, but available on it, are listed in the [JavaScript Reference](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference). See the complete list of [functions available to workers](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Functions_and_classes_available_to_workers).

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

*This interface inherits properties from the [`WorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope) interface, and its parent [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget), and therefore implements properties from [`WindowTimers`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope), [`WindowBase64`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope), and [`WindowEventHandlers`](https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers).*

[`SharedWorkerGlobalScope.name`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorkerGlobalScope/name) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
The name that the [`SharedWorker`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorker) was (optionally) given when it was created using the [`SharedWorker()`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorker/SharedWorker "SharedWorker()") constructor. This is mainly useful for debugging purposes.

[`SharedWorkerGlobalScope.applicationCache`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorkerGlobalScope/applicationCache) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
This property returns the <span class="page-not-created">`ApplicationCache`</span> object for the worker (see <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Using_the_application_cache" class="page-not-created" title="This is a link to an unwritten page">Using the application cache</a>).

### [Properties inherited from WorkerGlobalScope](#properties_inherited_from_workerglobalscope "Permalink to Properties inherited from WorkerGlobalScope")

[`WorkerGlobalScope.self`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/self)  
Returns an object reference to the `DedicatedWorkerGlobalScope` object itself.

[`WorkerGlobalScope.console`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/console) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the [`Console`](https://developer.mozilla.org/en-US/docs/Web/API/Console) associated with the worker.

[`WorkerGlobalScope.location`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/location) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the [`WorkerLocation`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerLocation) associated with the worker. `WorkerLocation` is a specific location object, mostly a subset of the [`Location`](https://developer.mozilla.org/en-US/docs/Web/API/Location) for browsing scopes, but adapted to workers.

[`WorkerGlobalScope.navigator`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/navigator) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the [`WorkerNavigator`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerNavigator) associated with the worker. `WorkerNavigator` is a specific navigator object, mostly a subset of the [`Navigator`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator) for browsing scopes, but adapted to workers.

[`WorkerGlobalScope.performance`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/performance) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
Returns the [`Performance`](https://developer.mozilla.org/en-US/docs/Web/API/Performance) object associated with the worker, which is a regular performance object, but with a subset of its properties and methods available.

### [Event handlers](#event_handlers "Permalink to Event handlers")

*This interface inherits event handlers from the [`WorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope) interface, and its parent [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget), and therefore implements event handlers from [`WindowTimers`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope), [`WindowBase64`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope), and [`WindowEventHandlers`](https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers).*

[`SharedWorkerGlobalScope.onconnect`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorkerGlobalScope/onconnect)  
Is an `event handler` representing the code to be called when the `connect` event is raised — that is, when a [`MessagePort`](https://developer.mozilla.org/en-US/docs/Web/API/MessagePort) connection is opened between the associated [`SharedWorker`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorker) and the main thread.

[Methods](#methods "Permalink to Methods")
------------------------------------------

*This interface inherits methods from the [`WorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope) interface, and its parent [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget), and therefore implements methods from [`WindowTimers`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope), [`WindowBase64`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope), and [`WindowEventHandlers`](https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers).*

[`SharedWorkerGlobalScope.close()`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorkerGlobalScope/close)  
Discards any tasks queued in the `SharedWorkerGlobalScope`'s event loop, effectively closing this particular scope.

### [Inherited from WorkerGlobalScope](#inherited_from_workerglobalscope "Permalink to Inherited from WorkerGlobalScope")

[`WorkerGlobalScope.close()`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/close)   
Discards any tasks queued in the `WorkerGlobalScope`'s event loop, effectively closing this particular scope.

[`WorkerGlobalScope.dump()`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/dump)   
Allows you to write a message to stdout — i.e. in your terminal. This is the same as Firefox's [`window.dump`](https://developer.mozilla.org/en-US/docs/Web/API/Window/dump), but for workers.

[`WorkerGlobalScope.importScripts()`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/importScripts)  
Imports one or more scripts into the worker's scope. You can specify as many as you'd like, separated by commas. For example:` importScripts('foo.js', 'bar.js');`

### [Implemented from other places](#implemented_from_other_places "Permalink to Implemented from other places")

[`WindowBase64.atob()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/atob)  
Decodes a string of data which has been encoded using base-64 encoding.

[`WindowBase64.btoa()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/btoa)  
Creates a base-64 encoded ASCII string from a string of binary data.

[`WindowTimers.clearInterval()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/clearInterval)  
Cancels the repeated execution set using [`WindowTimers.setInterval()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setInterval).

[`WindowTimers.clearTimeout()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/clearTimeout)  
Cancels the repeated execution set using [`WindowTimers.setTimeout()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setTimeout).

[`WindowTimers.setInterval()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setInterval)  
Schedules the execution of a function every X milliseconds.

[`WindowTimers.setTimeout()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setTimeout)  
Sets a delay for executing a function.

[Events](#events "Permalink to Events")
---------------------------------------

Listen to this event using `addEventListener()` or by assigning an event listener to the `oneventname` property of this interface.

`connect`  
Fired on shared workers when a new client connects.  
Also available via the `onconnect` property.

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#sharedworkerglobalscope" class="external">HTML Living Standard<br />
<span class="small">The definition of 'SharedWorkerGlobalScope' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [`SharedWorker`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorker)
-   [`WorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope)
-   [Using Web workers](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Using_web_workers)
-   [Functions available to workers](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Functions_and_classes_available_to_workers)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/sharedworkerglobalscope/index.html "Folder: en-us/web/api/sharedworkerglobalscope (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FSharedWorkerGlobalScope%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fsharedworkerglobalscope%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FSharedWorkerGlobalScope%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fsharedworkerglobalscope%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F0d5312d317fb301c56441905dc84e1f902cb7046%0A*+Document+last+modified%3A+2021-06-01T06%3A05%3A06.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22SharedWorkerGlobalScope%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Jun 1, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorkerGlobalScope/contributors.txt)

Change your languageSelect your preferred language English (US)Français日本語

Change language

#### Related Topics

1.  **[Web Workers API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API)**
2.  **[`SharedWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorkerGlobalScope)**
3.  Properties
    1.  [`applicationCache`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorkerGlobalScope/applicationCache)
    2.  [`name`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorkerGlobalScope/name)
    3.  [`onconnect`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorkerGlobalScope/onconnect)
4.  Methods
    1.  [`close()`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorkerGlobalScope/close)
5.  Events
    1.  [`connect`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorkerGlobalScope/connect_event)
6.  Inheritance:
    1.  [`WorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope)
    2.  [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)
7.  Related pages for Web Workers API
    1.  [`AbstractWorker`](https://developer.mozilla.org/en-US/docs/Web/API/AbstractWorker)
    2.  [`ChromeWorker`](https://developer.mozilla.org/en-US/docs/Web/API/ChromeWorker)
    3.  [`DedicatedWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/DedicatedWorkerGlobalScope)
    4.  [`ServiceWorker`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorker)
    5.  [`SharedWorker`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorker)
    6.  [`Worker`](https://developer.mozilla.org/en-US/docs/Web/API/Worker)
    7.  [`WorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope)
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
