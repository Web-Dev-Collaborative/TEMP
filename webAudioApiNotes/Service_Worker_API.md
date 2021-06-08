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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API" class="breadcrumb-current-page"><span data-property="name">Service Worker API</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Service worker concepts and usage](#service_worker_concepts_and_usage)
-   [Other use case ideas](#other_use_case_ideas)
-   [Interfaces](#interfaces)
-   [Specifications](#specifications)
-   [See also](#see_also)

Service Worker API
==================

Service workers essentially act as proxy servers that sit between web applications, the browser, and the network (when available). They are intended, among other things, to enable the creation of effective offline experiences, intercept network requests and take appropriate action based on whether the network is available, and update assets residing on the server. They will also allow access to push notifications and background sync APIs.

[Service worker concepts and usage](#service_worker_concepts_and_usage "Permalink to Service worker concepts and usage")
------------------------------------------------------------------------------------------------------------------------

A service worker is an event-driven [worker](https://developer.mozilla.org/en-US/docs/Web/API/Worker) registered against an origin and a path. It takes the form of a JavaScript file that can control the web-page/site that it is associated with, intercepting and modifying navigation and resource requests, and caching resources in a very granular fashion to give you complete control over how your app behaves in certain situations (the most obvious one being when the network is not available).

A service worker is run in a worker context: it therefore has no DOM access, and runs on a different thread to the main JavaScript that powers your app, so it is non-blocking. It is designed to be fully async; as a consequence, APIs such as synchronous [XHR](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest) and [Web Storage](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API) can't be used inside a service worker.

Service workers only run over HTTPS, for security reasons. Having modified network requests, wide open to *man in the middle* attacks would be really bad. In Firefox, Service Worker APIs are also hidden and cannot be used when the user is in <a href="https://support.mozilla.org/en-US/kb/private-browsing-use-firefox-without-history" class="external">private browsing mode</a>.

#### Tip

On Firefox, for testing you can run service workers over HTTP (insecurely); simply check the **Enable Service Workers over HTTP (when toolbox is open)** option in the Firefox Devtools options/gear menu.

#### Note

Unlike previous attempts in this area such as <a href="https://alistapart.com/article/application-cache-is-a-douchebag" class="external">AppCache</a>, service workers don't make assumptions about what you are trying to do, but then break when those assumptions are not exactly right. Instead, service workers give you much more granular control.

#### Note

Service workers make heavy use of [promises](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise), as generally they will wait for responses to come through, after which they will respond with a success or failure action. The promises architecture is ideal for this.

### [Registration](#registration "Permalink to Registration")

A service worker is first registered using the [`ServiceWorkerContainer.register()`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerContainer/register) method. If successful, your service worker will be downloaded to the client and attempt installation/activation (see below) for URLs accessed by the user inside the whole origin, or inside a subset specified by you.

### [Download, install and activate](#download_install_and_activate "Permalink to Download, install and activate")

At this point, your service worker will observe the following lifecycle:

1.  Download
2.  Install
3.  Activate

The service worker is immediately downloaded when a user first accesses a service worker–controlled site/page.

After that, it is updated when:

-   A navigation to an in-scope page occurs.
-   An event is fired on the service worker and it hasn't been downloaded in the last 24 hours.

Installation is attempted when the downloaded file is found to be new — either different to an existing service worker (byte-wise compared), or the first service worker encountered for this page/site.

If this is the first time a service worker has been made available, installation is attempted, then after a successful installation, it is activated.

If there is an existing service worker available, the new version is installed in the background, but not yet activated — at this point it is called the *worker in waiting*. It is only activated when there are no longer any pages loaded that are still using the old service worker. As soon as there are no more pages to be loaded, the new service worker activates (becoming the *active worker*). Activation can happen sooner using [`ServiceWorkerGlobalScope.skipWaiting()`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/skipWaiting) and existing pages can be claimed by the active worker using [`Clients.claim()`](https://developer.mozilla.org/en-US/docs/Web/API/Clients/claim).

You can listen for the [`install`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/install_event "install") event; a standard action is to prepare your service worker for usage when this fires, for example by creating a cache using the built in storage API, and placing assets inside it that you'll want for running your app offline.

There is also an [`activate`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/activate_event "activate") event. The point where this event fires is generally a good time to clean up old caches and other things associated with the previous version of your service worker.

Your service worker can respond to requests using the [`FetchEvent`](https://developer.mozilla.org/en-US/docs/Web/API/FetchEvent) event. You can modify the response to these requests in any way you want, using the [`FetchEvent.respondWith()`](https://developer.mozilla.org/en-US/docs/Web/API/FetchEvent/respondWith) method.

#### Note

Because `install`/`activate` events could take a while to complete, the service worker spec provides a [`waitUntil()`](https://developer.mozilla.org/en-US/docs/Web/API/ExtendableEvent/waitUntil "waitUntil()") method. Once it is called on `install` or `activate` events with a promise, functional events such as `fetch` and `push` will wait until the promise is successfully resolved.

For a complete tutorial to show how to build up your first basic example, read [Using Service Workers](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API/Using_Service_Workers).

[Other use case ideas](#other_use_case_ideas "Permalink to Other use case ideas")
---------------------------------------------------------------------------------

Service workers are also intended to be used for such things as:

-   Background data synchronization.
-   Responding to resource requests from other origins.
-   Receiving centralized updates to expensive-to-calculate data such as geolocation or gyroscope, so multiple pages can make use of one set of data.
-   Client-side compiling and dependency management of CoffeeScript, less, CJS/AMD modules, etc. for development purposes.
-   Hooks for background services.
-   Custom templating based on certain URL patterns.
-   Performance enhancements, for example pre-fetching resources that the user is likely to need in the near future, such as the next few pictures in a photo album.

In the future, service workers will be able to do a number of other useful things for the web platform that will bring it closer towards native app viability. Interestingly, other specifications can and will start to make use of the service worker context, for example:

-   <a href="https://github.com/slightlyoff/BackgroundSync" class="external">Background synchronization</a>: Start up a service worker even when no users are at the site, so caches can be updated, etc.
-   [Reacting to push messages](https://developer.mozilla.org/en-US/docs/Web/API/Push_API): Start up a service worker to send users a message to tell them new content is available.
-   Reacting to a particular time & date.
-   Entering a geo-fence.

[Interfaces](#interfaces "Permalink to Interfaces")
---------------------------------------------------

[`Cache`](https://developer.mozilla.org/en-US/docs/Web/API/Cache)   
Represents the storage for [`Request`](https://developer.mozilla.org/en-US/docs/Web/API/Request) / [`Response`](https://developer.mozilla.org/en-US/docs/Web/API/Response) object pairs that are cached as part of the [`ServiceWorker`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorker) life cycle.

[`CacheStorage`](https://developer.mozilla.org/en-US/docs/Web/API/CacheStorage)   
Represents the storage for [`Cache`](https://developer.mozilla.org/en-US/docs/Web/API/Cache) objects. It provides a master directory of all the named caches that a [`ServiceWorker`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorker) can access, and maintains a mapping of string names to corresponding [`Cache`](https://developer.mozilla.org/en-US/docs/Web/API/Cache) objects.

[`Client`](https://developer.mozilla.org/en-US/docs/Web/API/Client)   
Represents the scope of a service worker client. A service worker client is either a document in a browser context or a [`SharedWorker`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorker), which is controlled by an active worker.

[`Clients`](https://developer.mozilla.org/en-US/docs/Web/API/Clients)   
Represents a container for a list of [`Client`](https://developer.mozilla.org/en-US/docs/Web/API/Client) objects; the main way to access the active service worker clients at the current origin.

[`ExtendableEvent`](https://developer.mozilla.org/en-US/docs/Web/API/ExtendableEvent)   
Extends the lifetime of the `install` and `activate` events dispatched on the [`ServiceWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope), as part of the service worker lifecycle. This ensures that any functional events (like [`FetchEvent`](https://developer.mozilla.org/en-US/docs/Web/API/FetchEvent)) are not dispatched to the [`ServiceWorker`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorker), until it upgrades database schemas, and deletes outdated cache entries, etc.

[`ExtendableMessageEvent`](https://developer.mozilla.org/en-US/docs/Web/API/ExtendableMessageEvent)   
The event object of a [`ServiceWorkerGlobalScope/message_event`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/message_event) event fired on a service worker (when a channel message is received on the [`ServiceWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope) from another context) — extends the lifetime of such events.

[`FetchEvent`](https://developer.mozilla.org/en-US/docs/Web/API/FetchEvent)   
The parameter passed into the [`ServiceWorkerGlobalScope.onfetch`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/onfetch) handler, `FetchEvent` represents a fetch action that is dispatched on the [`ServiceWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope) of a [`ServiceWorker`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorker). It contains information about the request and resulting response, and provides the [`FetchEvent.respondWith()`](https://developer.mozilla.org/en-US/docs/Web/API/FetchEvent/respondWith "FetchEvent.respondWith()") method, which allows us to provide an arbitrary response back to the controlled page.

[`InstallEvent`](https://developer.mozilla.org/en-US/docs/Web/API/InstallEvent)   
The parameter passed into the [`oninstall`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/oninstall "oninstall") handler, the `InstallEvent` interface represents an install action that is dispatched on the [`ServiceWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope) of a [`ServiceWorker`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorker). As a child of [`ExtendableEvent`](https://developer.mozilla.org/en-US/docs/Web/API/ExtendableEvent), it ensures that functional events such as [`FetchEvent`](https://developer.mozilla.org/en-US/docs/Web/API/FetchEvent) are not dispatched during installation.

[`NavigationPreloadManager`](https://developer.mozilla.org/en-US/docs/Web/API/NavigationPreloadManager)   
Provides methods for managing the preloading of resources with a service worker.

[`Navigator.serviceWorker`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/serviceWorker)  
Returns a [`ServiceWorkerContainer`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerContainer) object, which provides access to registration, removal, upgrade, and communication with the [`ServiceWorker`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorker) objects for the <a href="https://html.spec.whatwg.org/multipage/browsers.html#concept-document-window" class="external">associated document</a>.

[`NotificationEvent`](https://developer.mozilla.org/en-US/docs/Web/API/NotificationEvent)   
The parameter passed into the [`onnotificationclick`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/onnotificationclick "onnotificationclick") handler, the `NotificationEvent` interface represents a notification click event that is dispatched on the [`ServiceWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope) of a [`ServiceWorker`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorker).

[`ServiceWorker`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorker)   
Represents a service worker. Multiple browsing contexts (e.g. pages, workers, etc.) can be associated with the same `ServiceWorker` object.

[`ServiceWorkerContainer`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerContainer)   
Provides an object representing the service worker as an overall unit in the network ecosystem, including facilities to register, unregister, and update service workers, and access the state of service workers and their registrations.

[`ServiceWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope)  
Represents the global execution context of a service worker.

[`ServiceWorkerMessageEvent`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerMessageEvent)   
Represents a message sent to a [`ServiceWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope). **Note that this interface is deprecated in modern browsers. Service worker messages will now use the [`MessageEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MessageEvent) interface, for consistency with other web messaging features.**

[`ServiceWorkerRegistration`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerRegistration)   
Represents a service worker registration.

[`SyncEvent`](https://developer.mozilla.org/en-US/docs/Web/API/SyncEvent)   
The SyncEvent interface represents a sync action that is dispatched on the [`ServiceWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope) of a ServiceWorker.

[`SyncManager`](https://developer.mozilla.org/en-US/docs/Web/API/SyncManager)   
Provides an interface for registering and listing sync registrations.

[`WindowClient`](https://developer.mozilla.org/en-US/docs/Web/API/WindowClient)   
Represents the scope of a service worker client that is a document in a browser context, controlled by an active worker. This is a special type of [`Client`](https://developer.mozilla.org/en-US/docs/Web/API/Client) object, with some additional methods and properties available.

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/" class="external" title="The &#39;Service Workers&#39; specification">Service Workers</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   <a href="https://serviceworke.rs/" class="external">ServiceWorker Cookbook</a>
-   [Using Service Workers](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API/Using_Service_Workers)
-   <a href="https://github.com/mdn/sw-test" class="external">Service workers basic code example</a>
-   <a href="https://jakearchibald.github.io/isserviceworkerready/" class="external">Is ServiceWorker ready?</a>
-   [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/service_worker_api/index.html "Folder: en-us/web/api/service_worker_api (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FService_Worker_API%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fservice_worker_api%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FService_Worker_API%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fservice_worker_api%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fb9df87222bf733d10b4cf993f4784cad6b6b8a0a%0A*+Document+last+modified%3A+2021-06-04T06%3A42%3A05.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22Service+Worker+API%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Jun 4, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API/contributors.txt)

Change your languageSelect your preferred language English (US)DeutschEspañolFrançais日本語한국어Português (do Brasil)Русский中文 (简体)

Change language

#### Related Topics

1.  [**Service Worker API**](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API)
2.  Service Worker guides
    1.  [Using Service Workers](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API/Using_Service_Workers)
3.  Interfaces
    1.  [`Cache`](https://developer.mozilla.org/en-US/docs/Web/API/Cache)
    2.  [`CacheStorage`](https://developer.mozilla.org/en-US/docs/Web/API/CacheStorage)
    3.  [`Client`](https://developer.mozilla.org/en-US/docs/Web/API/Client)
    4.  [`Clients`](https://developer.mozilla.org/en-US/docs/Web/API/Clients)
    5.  [`ExtendableEvent`](https://developer.mozilla.org/en-US/docs/Web/API/ExtendableEvent)
    6.  [`FetchEvent`](https://developer.mozilla.org/en-US/docs/Web/API/FetchEvent)
    7.  [`InstallEvent`](https://developer.mozilla.org/en-US/docs/Web/API/InstallEvent)
    8.  [`Navigator.serviceWorker`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/serviceWorker)
    9.  [`NotificationEvent`](https://developer.mozilla.org/en-US/docs/Web/API/NotificationEvent)
    10. [`PeriodicSyncEvent`](https://developer.mozilla.org/en-US/docs/Web/API/PeriodicSyncEvent)
    11. [`PeriodicSyncManager`](https://developer.mozilla.org/en-US/docs/Web/API/PeriodicSyncManager)
    12. <span class="page-not-created">`PeriodicSyncRegistration`</span>
    13. [`ServiceWorker`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorker)
    14. [`ServiceWorkerContainer`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerContainer)
    15. [`ServiceWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope)
    16. [`ServiceWorkerRegistration`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerRegistration)
    17. [`SyncEvent`](https://developer.mozilla.org/en-US/docs/Web/API/SyncEvent)
    18. [`SyncManager`](https://developer.mozilla.org/en-US/docs/Web/API/SyncManager)
    19. <span class="page-not-created">`SyncRegistration`</span>
    20. [`WindowClient`](https://developer.mozilla.org/en-US/docs/Web/API/WindowClient)
4.  Related APIs
    1.  [Channel Messaging API](https://developer.mozilla.org/en-US/docs/Web/API/Channel_Messaging_API)
    2.  [Notifications API](https://developer.mozilla.org/en-US/docs/Web/API/Notifications_API)
    3.  [Push API](https://developer.mozilla.org/en-US/docs/Web/API/Push_API)
    4.  [Web Workers API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API)
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
