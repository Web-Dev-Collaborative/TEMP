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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/Navigator" class="breadcrumb-current-page"><span data-property="name">Navigator</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Properties](#properties)
-   [Methods](#methods)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)

Navigator
=========

The `Navigator` interface represents the state and the identity of the user agent. It allows scripts to query it and to register themselves to carry on some activities.

A `Navigator` object can be retrieved using the read-only [`window.navigator`](https://developer.mozilla.org/en-US/docs/Web/API/Window/navigator) property.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

*Doesn't inherit any properties, but implements those defined in [`NavigatorID`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorID), [`NavigatorLanguage`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorLanguage), [`NavigatorOnLine`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorOnLine), <span class="page-not-created">`NavigatorContentUtils`</span>, [`NavigatorStorage`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorStorage), <span class="page-not-created">`NavigatorStorageUtils`</span>, [`NavigatorConcurrentHardware`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorConcurrentHardware), [`NavigatorPlugins`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorPlugins), and <span class="page-not-created">`NavigatorUserMedia`</span>.*

### [Standard properties](#standard_properties "Permalink to Standard properties")

[`Navigator.connection`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/connection) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
Provides a [`NetworkInformation`](https://developer.mozilla.org/en-US/docs/Web/API/NetworkInformation) object containing information about the network connection of a device.

[`Navigator.cookieEnabled`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/cookieEnabled) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns false if setting a cookie will be ignored and true otherwise.

[`Navigator.credentials`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/credentials) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the [`CredentialsContainer`](https://developer.mozilla.org/en-US/docs/Web/API/CredentialsContainer) interface which exposes methods to request credentials and notify the user agent when interesting events occur such as successful sign in or sign out. 

[`Navigator.deviceMemory`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/deviceMemory) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
Returns the amount of device memory in gigabytes. This value is an approximation given by rounding to the nearest power of 2 and dividing that number by 1024.

[`Navigator.doNotTrack`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/doNotTrack) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
Reports the value of the user's do-not-track preference. When this value is "yes", your web site or application should not track the user.

[`Navigator.geolocation`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/geolocation) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`Geolocation`](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation) object allowing accessing the location of the device.

[`Navigator.hid`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/hid) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns an [`HID`](https://developer.mozilla.org/en-US/docs/Web/API/HID) object providing methods for connecting to HID devices, listing attached HID devices, and event handlers for connected HID devices.

[`NavigatorConcurrentHardware.hardwareConcurrency`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorConcurrentHardware/hardwareConcurrency) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the number of logical processor cores available.

[`NavigatorPlugins.javaEnabled`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorPlugins/javaEnabled) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns false.

[`Navigator.keyboard`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/keyboard) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
Returns a [`Keyboard`](https://developer.mozilla.org/en-US/docs/Web/API/Keyboard) object which provides access to functions that retrieve keyboard layout maps and toggle capturing of key presses from the physical keyboard.

[`NavigatorLanguage.language`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorLanguage/language) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) representing the preferred language of the user, usually the language of the browser UI. The `null` value is returned when this is unknown.

[`NavigatorLanguage.languages`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorLanguage/languages) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
Returns an array of [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) representing the languages known to the user, by order of preference.

[`Navigator.locks`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/locks) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
Returns a [`LockManager`](https://developer.mozilla.org/en-US/docs/Web/API/LockManager) object which provides methods for requesting a new [`Lock`](https://developer.mozilla.org/en-US/docs/Web/API/Lock) object and querying for an existing [`Lock`](https://developer.mozilla.org/en-US/docs/Web/API/Lock) object

[`Navigator.maxTouchPoints`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/maxTouchPoints) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the maximum number of simultaneous touch contact points are supported by the current device.

[`Navigator.mediaCapabilities`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/mediaCapabilities) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
Returns a [`MediaCapabilities`](https://developer.mozilla.org/en-US/docs/Web/API/MediaCapabilities) object that can expose information about the decoding and encoding capabilities for a given format and output capabilities.

[`Navigator.mediaDevices`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/mediaDevices) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a reference to a [`MediaDevices`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices) object which can then be used to get information about available media devices ([`MediaDevices.enumerateDevices()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/enumerateDevices)), find out what constrainable properties are supported for media on the user's computer and user agent ([`MediaDevices.getSupportedConstraints()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getSupportedConstraints)), and to request access to media using [`MediaDevices.getUserMedia()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getUserMedia).

[`Navigator.mediaSession`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/mediaSession) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
Returns [`MediaSession`](https://developer.mozilla.org/en-US/docs/Web/API/MediaSession) object which can be used to provide metadata that can be used by the browser to present information about the currently-playing media to the user, such as in a global media controls UI.

[`NavigatorPlugins.mimeTypes`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorPlugins/mimeTypes) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
Returns an [`MimeTypeArray`](https://developer.mozilla.org/en-US/docs/Web/API/MimeTypeArray) listing the MIME types supported by the browser.

[`NavigatorOnLine.onLine`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorOnLine/onLine) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the browser is working online.

[`Navigator.permissions`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/permissions) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
Returns a [`Permissions`](https://developer.mozilla.org/en-US/docs/Web/API/Permissions) object that can be used to query and update permission status of APIs covered by the [Permissions API](https://developer.mozilla.org/en-US/docs/Web/API/Permissions_API).

[`NavigatorPlugins.plugins`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorPlugins/plugins) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
Returns a [`PluginArray`](https://developer.mozilla.org/en-US/docs/Web/API/PluginArray) listing the plugins installed in the browser.

[`Navigator.presentation`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/presentation) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
Returns a reference to the [`Presentation`](https://developer.mozilla.org/en-US/docs/Web/API/Presentation) API.

[`Navigator.serial`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/serial) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`Serial`](https://developer.mozilla.org/en-US/docs/Web/API/Serial) object, which represents the entry point into the [`Web Serial API`](https://developer.mozilla.org/en-US/docs/Web/API/Web_Serial_API) to enable the control of serial ports.

[`Navigator.serviceWorker`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/serviceWorker) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`ServiceWorkerContainer`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerContainer) object, which provides access to registration, removal, upgrade, and communication with the [`ServiceWorker`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorker) objects for the <a href="https://html.spec.whatwg.org/multipage/browsers.html#concept-document-window" class="external">associated document</a>.

[`NavigatorStorage.storage`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorStorage/storage) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the singleton [`StorageManager`](https://developer.mozilla.org/en-US/docs/Web/API/StorageManager) object used for managing persistence permissions and estimating available storage on a site-by-site/app-by-app basis.

[`NavigatorID.userAgent`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorID/userAgent) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the user agent string for the current browser.

[`Navigator.vendor`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/vendor) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the vendor name of the current browser (e.g., "Netscape6").

[`Navigator.webdriver`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/webdriver) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>    
Indicates whether the user agent is controlled by automation.

[`Navigator.xr`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/xr) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>    
Returns [`XRSystem`](https://developer.mozilla.org/en-US/docs/Web/API/XRSystem) object, which represents the entry point into the [WebXR API](https://developer.mozilla.org/en-US/docs/Web/API/WebXR_Device_API).

### [Non-standard properties](#non-standard_properties "Permalink to Non-standard properties")

[`Navigator.buildID`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/buildID)   
Returns the build identifier of the browser. In modern browsers this property now returns a fixed timestamp as a privacy measure, e.g. `20181001000000` in Firefox 64 onwards.

[`Navigator.contacts`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/contacts) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
Returns a [`ContactsManager`](https://developer.mozilla.org/en-US/docs/Web/API/ContactsManager) interface which allows users to select entries from their contact list and share limited details of the selected entries with a website or application.

<span class="page-not-created">`Navigator.securitypolicy`</span>   
Returns an empty string. In Netscape 4.7x, returns "US & CA domestic policy" or "Export policy".

<span class="page-not-created">`Navigator.standalone`</span>   
Returns a boolean indicating whether the browser is running in standalone mode. Available on Apple's iOS Safari only.

[`Navigator.wakeLock`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/wakeLock) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
Returns a [`WakeLock`](https://developer.mozilla.org/en-US/docs/Web/API/WakeLock) interface you can use to request screen wake locks and prevent screen from dimming, turning off, or showing a screen saver.

### [Deprecated properties](#deprecated_properties "Permalink to Deprecated properties")

[`NavigatorID.appCodeName`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorID/appCodeName) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
Returns the internal "code" name of the current browser. Do not rely on this property to return the correct value.

[`NavigatorID.appName`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorID/appName) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
Returns a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) with the official name of the browser. Do not rely on this property to return the correct value.

[`NavigatorID.appVersion`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorID/appVersion) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
Returns the version of the browser as a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString). Do not rely on this property to return the correct value.

[`Navigator.activeVRDisplays`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/activeVRDisplays) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
Returns an array containing every [`VRDisplay`](https://developer.mozilla.org/en-US/docs/Web/API/VRDisplay) object that is currently presenting ([`VRDisplay.ispresenting`](https://developer.mozilla.org/en-US/docs/Web/API/VRDisplay/isPresenting) is `true`).

[`Navigator.battery`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/battery) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
Returns a [`BatteryManager`](https://developer.mozilla.org/en-US/docs/Web/API/BatteryManager) object you can use to get information about the battery charging status.

[`Navigator.oscpu`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/oscpu) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
Returns a string that represents the current operating system.

[`NavigatorID.platform`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorID/platform) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
Returns a string representing the platform of the browser. Do not rely on this function to return a significant value.

[`NavigatorID.product`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorID/product) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
Always returns `'Gecko'`, on any browser. This property is kept only for compatibility purpose.

[`Navigator.productSub`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/productSub) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
Returns the build number of the current browser (e.g., "20060909").

[`Navigator.vendorSub`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/vendorSub) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
Returns the vendor version number (e.g. "6.1").

[Methods](#methods "Permalink to Methods")
------------------------------------------

*Doesn't inherit any method, but implements those defined in [`NavigatorID`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorID), <span class="page-not-created">`NavigatorContentUtils`</span>, <span class="page-not-created">`NavigatorUserMedia`</span>, and <span class="page-not-created">`NavigatorStorageUtils`</span>.*

[`Navigator.canShare()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/canShare)  
Returns `true` if a call to `Navigator.share()` would succeed.

[`Navigator.clearAppBadge()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/clearAppBadge)  
Clears a badge on the current app's icon and returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined).

[`Navigator.getBattery()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/getBattery)  
Returns a promise that resolves with a [`BatteryManager`](https://developer.mozilla.org/en-US/docs/Web/API/BatteryManager) object that returns information about the battery charging status.

[`Navigator.registerProtocolHandler()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/registerProtocolHandler)  
Allows web sites to register themselves as a possible handler for a given protocol.

[`Navigator.requestMediaKeySystemAccess()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/requestMediaKeySystemAccess)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) for a MediaKeySystemAccess object.

[`Navigator.sendBeacon()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/sendBeacon)  
Used to asynchronously transfer a small amount of data using [HTTP](https://developer.mozilla.org/en-US/docs/Glossary/HTTP) from the User Agent to a web server.

[`Navigator.setAppBadge()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/setAppBadge)  
Sets a badge on the icon associated with this app and returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined).

[`Navigator.share()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/share)  
Invokes the native sharing mechanism of the current platform.

[`Navigator.vibrate()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/vibrate)  
Causes vibration on devices with support for it. Does nothing if vibration support isn't available.

### [Deprecated methods](#deprecated_methods "Permalink to Deprecated methods")

[`Navigator.getVRDisplays()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/getVRDisplays)   
Returns a promise that resolves to an array of [`VRDisplay`](https://developer.mozilla.org/en-US/docs/Web/API/VRDisplay) objects representing any available VR devices connected to the computer.

[`Navigator.getUserMedia()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/getUserMedia)   
After having prompted the user for permission, returns the audio or video stream associated to a camera or microphone on the local computer.

[`Navigator.registerContentHandler()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/registerContentHandler)   
Allows web sites to register themselves as a possible handler for a given MIME type.

[`NavigatorID.taintEnabled()`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorID/taintEnabled)   
Returns `false`. JavaScript taint/untaint functions removed in JavaScript 1.2.

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#the-navigator-object" class="external">HTML Living Standard<br />
<span class="small">The definition of 'the Navigator object' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/navigator/index.html "Folder: en-us/web/api/navigator (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FNavigator%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fnavigator%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FNavigator%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fnavigator%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F9b648e559239b3e682abfcb15845a954d420b207%0A*+Document+last+modified%3A+2021-05-31T17%3A00%3A38.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22Navigator%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/contributors.txt)

Change your languageSelect your preferred language English (US)DeutschEspañolFrançais日本語한국어PolskiPortuguês (do Brasil)Русский中文 (简体)正體中文 (繁體)

Change language

#### Related Topics

1.  **[Document Object Model](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model)**
2.  **[`Navigator`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator)**
3.  Properties
    1.  [`activeVRDisplays`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/activeVRDisplays)
    2.  [`appCodeName`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorID/appCodeName)
    3.  [`appName`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorID/appName)
    4.  [`appVersion`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorID/appVersion)
    5.  [`battery`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/battery)
    6.  [`buildID`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/buildID)
    7.  [`clipboard`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/clipboard)
    8.  [`connection`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/connection)
    9.  [`contacts`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/contacts)
    10. [`cookieEnabled`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/cookieEnabled)
    11. [`credentials`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/credentials)
    12. [`deviceMemory`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/deviceMemory)
    13. [`doNotTrack`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/doNotTrack)
    14. [`geolocation`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/geolocation)
    15. [`hid`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/hid)
    16. [`keyboard`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/keyboard)
    17. [`language`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorLanguage/language)
    18. [`languages`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorLanguage/languages)
    19. [`locks`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/locks)
    20. [`maxTouchPoints`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/maxTouchPoints)
    21. [`mediaDevices`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/mediaDevices)
    22. [`mediaSession`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/mediaSession)
    23. [`onLine`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorOnLine/onLine)
    24. [`oscpu`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/oscpu)
    25. [`permissions`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/permissions)
    26. [`platform`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorID/platform)
    27. [`product`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorID/product)
    28. [`productSub`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/productSub)
    29. [`serial`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/serial)
    30. [`serviceWorker`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/serviceWorker)
    31. [`userAgent`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorID/userAgent)
    32. [`vendor`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/vendor)
    33. [`vendorSub`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/vendorSub)
    34. [`webdriver`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/webdriver)
    35. [`xr`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/xr)
4.  Methods
    1.  [`canShare()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/canShare)
    2.  [`clearAppBadge()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/clearAppBadge)
    3.  [`clearWatch()`](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation/clearWatch)
    4.  [`getBattery()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/getBattery)
    5.  [`getCurrentPosition()`](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation/getCurrentPosition)
    6.  [`getGamepads()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/getGamepads)
    7.  [`getUserMedia()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/getUserMedia)
    8.  [`getVRDisplays()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/getVRDisplays)
    9.  [`mozIsLocallyAvailable()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/mozIsLocallyAvailable)
    10. [`msLaunchUri()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/msLaunchUri)
    11. [`registerContentHandler()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/registerContentHandler)
    12. [`registerProtocolHandler()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/registerProtocolHandler)
    13. [`requestMediaKeySystemAccess()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/requestMediaKeySystemAccess)
    14. [`sendBeacon()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/sendBeacon)
    15. [`setAppBadge()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/setAppBadge)
    16. [`share()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/share)
    17. [`taintEnabled()`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorID/taintEnabled)
    18. [`vibrate()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/vibrate)
    19. [`watchPosition()`](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation/watchPosition)
5.  Related pages for DOM
    1.  [`AbortController`](https://developer.mozilla.org/en-US/docs/Web/API/AbortController)
    2.  [`AbortSignal`](https://developer.mozilla.org/en-US/docs/Web/API/AbortSignal)
    3.  [`AbstractRange`](https://developer.mozilla.org/en-US/docs/Web/API/AbstractRange)
    4.  [`Attr`](https://developer.mozilla.org/en-US/docs/Web/API/Attr)
    5.  [`ByteString`](https://developer.mozilla.org/en-US/docs/Web/API/ByteString)
    6.  [`CDATASection`](https://developer.mozilla.org/en-US/docs/Web/API/CDATASection)
    7.  [`CSSPrimitiveValue`](https://developer.mozilla.org/en-US/docs/Web/API/CSSPrimitiveValue)
    8.  [`CSSValue`](https://developer.mozilla.org/en-US/docs/Web/API/CSSValue)
    9.  [`CSSValueList`](https://developer.mozilla.org/en-US/docs/Web/API/CSSValueList)
    10. [`CharacterData`](https://developer.mozilla.org/en-US/docs/Web/API/CharacterData)
    11. [`ChildNode`](https://developer.mozilla.org/en-US/docs/Web/API/ChildNode)
    12. [`Comment`](https://developer.mozilla.org/en-US/docs/Web/API/Comment)
    13. [`CustomEvent`](https://developer.mozilla.org/en-US/docs/Web/API/CustomEvent)
    14. [`DOMConfiguration`](https://developer.mozilla.org/en-US/docs/Web/API/DOMConfiguration)
    15. [`DOMError`](https://developer.mozilla.org/en-US/docs/Web/API/DOMError)
    16. [`DOMErrorHandler`](https://developer.mozilla.org/en-US/docs/Web/API/DOMErrorHandler)
    17. [`DOMException`](https://developer.mozilla.org/en-US/docs/Web/API/DOMException)
    18. [`DOMImplementation`](https://developer.mozilla.org/en-US/docs/Web/API/DOMImplementation)
    19. [`DOMImplementationList`](https://developer.mozilla.org/en-US/docs/Web/API/DOMImplementationList)
    20. [`DOMImplementationRegistry`](https://developer.mozilla.org/en-US/docs/Web/API/DOMImplementationRegistry)
    21. [`DOMImplementationSource`](https://developer.mozilla.org/en-US/docs/Web/API/DOMImplementationSource)
    22. [`DOMLocator`](https://developer.mozilla.org/en-US/docs/Web/API/DOMLocator)
    23. [`DOMObject`](https://developer.mozilla.org/en-US/docs/Web/API/DOMObject)
    24. [`DOMParser`](https://developer.mozilla.org/en-US/docs/Web/API/DOMParser)
    25. [`DOMPoint`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPoint)
    26. [`DOMPointInit`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPointInit)
    27. [`DOMPointReadOnly`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPointReadOnly)
    28. [`DOMRect`](https://developer.mozilla.org/en-US/docs/Web/API/DOMRect)
    29. [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString)
    30. [`DOMTimeStamp`](https://developer.mozilla.org/en-US/docs/Web/API/DOMTimeStamp)
    31. [`DOMTokenList`](https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList)
    32. [`DOMUserData`](https://developer.mozilla.org/en-US/docs/Web/API/DOMUserData)
    33. [`Document`](https://developer.mozilla.org/en-US/docs/Web/API/Document)
    34. [`DocumentFragment`](https://developer.mozilla.org/en-US/docs/Web/API/DocumentFragment)
    35. [`DocumentType`](https://developer.mozilla.org/en-US/docs/Web/API/DocumentType)
    36. [`Element`](https://developer.mozilla.org/en-US/docs/Web/API/Element)
    37. [`ElementTraversal`](https://developer.mozilla.org/en-US/docs/Web/API/ElementTraversal)
    38. [`Entity`](https://developer.mozilla.org/en-US/docs/Web/API/Entity)
    39. [`EntityReference`](https://developer.mozilla.org/en-US/docs/Web/API/EntityReference)
    40. [`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event)
    41. [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)
    42. [`HTMLCollection`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCollection)
    43. [`MutationObserver`](https://developer.mozilla.org/en-US/docs/Web/API/MutationObserver)
    44. [`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node)
    45. [`NodeFilter`](https://developer.mozilla.org/en-US/docs/Web/API/NodeFilter)
    46. [`NodeIterator`](https://developer.mozilla.org/en-US/docs/Web/API/NodeIterator)
    47. [`NodeList`](https://developer.mozilla.org/en-US/docs/Web/API/NodeList)
    48. [`ProcessingInstruction`](https://developer.mozilla.org/en-US/docs/Web/API/ProcessingInstruction)
    49. [`PromiseResolver`](https://developer.mozilla.org/en-US/docs/Web/API/PromiseResolver)
    50. [`Range`](https://developer.mozilla.org/en-US/docs/Web/API/Range)
    51. [`StaticRange`](https://developer.mozilla.org/en-US/docs/Web/API/StaticRange)
    52. [`Text`](https://developer.mozilla.org/en-US/docs/Web/API/Text)
    53. [`TextDecoder`](https://developer.mozilla.org/en-US/docs/Web/API/TextDecoder)
    54. [`TextEncoder`](https://developer.mozilla.org/en-US/docs/Web/API/TextEncoder)
    55. [`TimeRanges`](https://developer.mozilla.org/en-US/docs/Web/API/TimeRanges)
    56. [`TreeWalker`](https://developer.mozilla.org/en-US/docs/Web/API/TreeWalker)
    57. [`TypeInfo`](https://developer.mozilla.org/en-US/docs/Web/API/TypeInfo)
    58. [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString)
    59. [`UserDataHandler`](https://developer.mozilla.org/en-US/docs/Web/API/UserDataHandler)
    60. [`XMLDocument`](https://developer.mozilla.org/en-US/docs/Web/API/XMLDocument)

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
