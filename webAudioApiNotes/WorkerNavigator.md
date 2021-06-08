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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/WorkerNavigator" class="breadcrumb-current-page"><span data-property="name">WorkerNavigator</span></a>

Table of contents
-----------------

Table of contents

-   [Properties](#properties)
-   [Methods](#methods)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

WorkerNavigator
===============

The `WorkerNavigator` interface represents a subset of the [`Navigator`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator) interface allowed to be accessed from a [`Worker`](https://developer.mozilla.org/en-US/docs/Web/API/Worker). Such an object is initialized for each worker and is available via the [`WorkerGlobalScope.navigator`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/navigator) property obtained by calling `self.navigator`.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

*The `WorkerNavigator` interface implements properties from the [`NavigatorID`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorID), [`NavigatorLanguage`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorLanguage), [`NavigatorOnLine`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorOnLine), <span class="page-not-created">`NavigatorDataStore`</span>, and [`NavigatorConcurrentHardware`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorConcurrentHardware) interfaces.*

[`WorkerNavigator.connection`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerNavigator/connection)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Provides a [`NetworkInformation`](https://developer.mozilla.org/en-US/docs/Web/API/NetworkInformation) object containing information about the network connection of a device.

[`WorkerNavigator.locks`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerNavigator/locks)  <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`LockManager`](https://developer.mozilla.org/en-US/docs/Web/API/LockManager) object which provides methods for requesting a new [`Lock`](https://developer.mozilla.org/en-US/docs/Web/API/Lock) object and querying for an existing `Lock` object.

[`WorkerNavigator.permissions`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerNavigator/permissions)  <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`Permissions`](https://developer.mozilla.org/en-US/docs/Web/API/Permissions) object that can be used to query and update permission status of APIs covered by the [Permissions API](https://developer.mozilla.org/en-US/docs/Web/API/Permissions_API).

[`WorkerNavigator.serial`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerNavigator/serial) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`Serial`](https://developer.mozilla.org/en-US/docs/Web/API/Serial) object, which represents the entry point into the [`Web Serial API`](https://developer.mozilla.org/en-US/docs/Web/API/Web_Serial_API) to enable the control of serial ports.

[`NavigatorStorage.storage`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorStorage/storage)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
Returns a [`StorageManager`](https://developer.mozilla.org/en-US/docs/Web/API/StorageManager) interface for managing persistance permissions and estimating available storage.

### [Inherited properties](#inherited_properties "Permalink to Inherited properties")

[`NavigatorID.appCodeName`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorID/appCodeName)  <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Always returns `'Mozilla'`, in any browser. This property is kept only for compatibility purposes.

[`NavigatorID.appName`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorID/appName)  <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the official name of the browser. Do not rely on this property to return the correct value.

[`NavigatorID.appVersion`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorID/appVersion)  <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the version of the browser as a string. Do not rely on this property to return the correct value.

[`NavigatorConcurrentHardware.hardwareConcurrency`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorConcurrentHardware/hardwareConcurrency)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the number of logical processor cores available.

[`NavigatorLanguage.language`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorLanguage/language)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) representing the language version of the browser. The `null` value is returned when this is unknown.

[`NavigatorLanguage.languages`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorLanguage/languages)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns an array of [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString)s representing the languages known to the user, in order of preference.

[`NavigatorOnLine.onLine`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorOnLine/onLine)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the browser is online.

[`NavigatorID.platform`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorID/platform)  <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a string representing the platform of the browser. Do not rely on this property to return the correct value.

[`NavigatorID.product`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorID/product)  <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Always returns `'Gecko'`, on any browser. This property is kept only for compatibility purposes.

[`NavigatorID.userAgent`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorID/userAgent)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the user agent string for the current browser.

[Methods](#methods "Permalink to Methods")
------------------------------------------

*The `WorkerNavigator` interface implements methods from the [`NavigatorID`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorID), [`NavigatorLanguage`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorLanguage) and [`NavigatorOnLine`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorOnLine) interfaces.*

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#workernavigator" class="external">HTML Living Standard<br />
<span class="small">The definition of 'WorkerNavigator' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   Other Worker-related interfaces: [`Worker`](https://developer.mozilla.org/en-US/docs/Web/API/Worker), [`WorkerLocation`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerLocation), and [`WorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope).
-   [Using web workers.](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Using_web_workers)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/workernavigator/index.html "Folder: en-us/web/api/workernavigator (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWorkerNavigator%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fworkernavigator%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWorkerNavigator%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fworkernavigator%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F94c536f9b3a50303a85e7963a4ff4958d1aec382%0A*+Document+last+modified%3A+2021-05-31T17%3A13%3A02.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22WorkerNavigator%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/WorkerNavigator/contributors.txt)

#### Related Topics

1.  **[Web Workers API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API)**
2.  **[`WorkerNavigator`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerNavigator)**
3.  Properties
    1.  [`appCodeName`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorID/appCodeName)
    2.  [`appName`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorID/appName)
    3.  [`appVersion`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorID/appVersion)
    4.  [`connection`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerNavigator/connection)
    5.  [`language`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorLanguage/language)
    6.  [`languages`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorLanguage/languages)
    7.  [`locks`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerNavigator/locks)
    8.  [`onLine`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorOnLine/onLine)
    9.  [`permissions`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerNavigator/permissions)
    10. [`platform`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorID/platform)
    11. [`product`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorID/product)
    12. [`serial`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerNavigator/serial)
    13. [`userAgent`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorID/userAgent)
4.  Methods
    1.  [`taintEnabled()`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorID/taintEnabled)
5.  Related pages for Web Workers API
    1.  [`AbstractWorker`](https://developer.mozilla.org/en-US/docs/Web/API/AbstractWorker)
    2.  [`ChromeWorker`](https://developer.mozilla.org/en-US/docs/Web/API/ChromeWorker)
    3.  [`DedicatedWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/DedicatedWorkerGlobalScope)
    4.  [`ServiceWorker`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorker)
    5.  [`SharedWorker`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorker)
    6.  [`SharedWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorkerGlobalScope)
    7.  [`Worker`](https://developer.mozilla.org/en-US/docs/Web/API/Worker)
    8.  [`WorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope)
    9.  [`WorkerLocation`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerLocation)

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
