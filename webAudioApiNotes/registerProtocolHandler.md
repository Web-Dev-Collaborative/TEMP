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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/Navigator" class="breadcrumb-penultimate"><span data-property="name">Navigator</span></a>
4.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/Navigator/registerProtocolHandler" class="breadcrumb-current-page"><span data-property="name">Navigator.registerProtocolHandler()</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Syntax](#syntax)
-   [Permitted schemes](#permitted_schemes)
-   [Example](#example)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

Navigator.registerProtocolHandler()
===================================

#### Secure context

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

<span class="seoSummary">The **[`Navigator`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator)** method `registerProtocolHandler()` lets websites register their ability to open or handle particular URL schemes (aka protocols).</span>

For example, this API lets webmail sites open `mailto:` URLs, or VoIP sites open `tel:` URLs.

[Syntax](#syntax "Permalink to Syntax")
---------------------------------------

    navigator.registerProtocolHandler(scheme, url);

**Note:** The original implementation required three arguments: `navigator.registerProtocolHandler(scheme, url, title)`, which most browsers still support (see the [compatibility table below](#browser_compatibility)). It is recommended to still set the title, since browsers that support the updated spec will most likely be backwards-compatible and still accept the title (but not use it).

### [Parameters](#parameters "Permalink to Parameters")

`scheme`  
A string containing the protocol the site wishes to handle. For example, you can register to handle SMS text message links by passing the `"sms"` scheme.

`url`  
A string containing the URL of the handler. **This URL must include `%s`**, as a placeholder that will be replaced with the [escaped](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/encodeURIComponent) URL to be handled.

**Note:** The handler URL must use the `https` scheme. Older browsers also supported `http`.

`title`   
A human-readable title string for the handler. **This will be displayed to the user**, such as prompting “Allow this site to handle \[scheme\] links?” or listing registered handlers in the browser’s settings.

**Note:** The title has been removed from the spec due to spoofing concerns, but some browsers **still require it** (check the [compatibility table below](#browser_compatibility)). It is recommended to **always set the title**, since browsers that support the updated spec most likely will be backwards-compatible and still accept the title (but not use it).

### [Exceptions](#exceptions "Permalink to Exceptions")

[`SecurityError`](https://developer.mozilla.org/en-US/docs/Web/API/DOMException#exception-securityerror)  
The user agent blocked the registration. This might happen if:

-   The registered scheme (protocol) is invalid, such as a scheme the browser handles itself (`https:`, `about:`, etc.)
-   The handler URL’s [origin](https://developer.mozilla.org/en-US/docs/Glossary/Origin) does not match the origin of the page calling this API.
-   The browser requires that this function is called from a secure context.
-   The browser requires that the handler's URL be over HTTPS.

[`SyntaxError`](https://developer.mozilla.org/en-US/docs/Web/API/DOMException#exception-syntaxerror)  
The `%s` placeholder is missing from the handler URL.

[Permitted schemes](#permitted_schemes "Permalink to Permitted schemes")
------------------------------------------------------------------------

For security reasons, `registerProtocolHandler()` restricts which schemes can be registered.

A **custom scheme** may be registered as long as:

-   The custom scheme's name begins with `web+`
-   The custom scheme's name includes at least 1 letter after the `web+` prefix
-   The custom scheme has only lowercase ASCII letters in its name.

For example, `web+burger`, as shown in the [Example](#example) below.

Otherwise, the scheme must be one of the following:

-   `bitcoin`
-   `geo`
-   `im`
-   `irc`
-   `ircs`
-   `magnet`
-   `mailto`
-   `mms`
-   `news`
-   `nntp`
-   `openpgp4fpr`
-   `sip`
-   `sms`
-   `smsto`
-   `ssh`
-   `tel`
-   `urn`
-   `webcal`
-   `wtai`
-   `xmpp`

[Example](#example "Permalink to Example")
------------------------------------------

If your site is `burgers.example.com`, you can register a protocol handler for it to handle `web+burger:` links, like so:

    navigator.registerProtocolHandler("web+burger",
                                      "https://burgers.example.com/?burger=%s",
                                      "Burger handler"); // last title arg included for compatibility

This creates a handler that lets `web+burger:` links send the user to your site, inserting the accessed burger URL into the `%s` placeholder.

This script must be run from the same origin as the handler URL (so any page at `https://burgers.example.com`), and the handler URL must be `http` or `https`.

The user will be notified that your code asked to register the protocol handler, so that they can decide whether or not to allow it. See the screenshot below for an example on `google.co.uk`:

<img src="https://developer.mozilla.org/en-US/docs/Web/API/Navigator/registerProtocolHandler/protocolregister.png" alt="A browser notification reads “Add Burger handler (www.google.co.uk) as an application for burger links?”, and offers an “Add Application” button and a close to ignore the handler request." width="700" height="401" />

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/system-state.html#custom-handlers" class="external">HTML Living Standard<br />
<span class="small">The definition of 'registerProtocolHandler()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Living standard</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Web-based protocol handlers](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/registerProtocolHandler/Web-based_protocol_handlers)
-   <a href="https://blog.mozilla.com/webdev/2010/07/26/registerprotocolhandler-enhancing-the-federated-web/" class="external">RegisterProtocolHandler Enhancing the Federated Web</a> at Mozilla Webdev

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/navigator/registerprotocolhandler/index.html "Folder: en-us/web/api/navigator/registerprotocolhandler (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FNavigator%2FregisterProtocolHandler%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fnavigator%2Fregisterprotocolhandler%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FNavigator%2FregisterProtocolHandler%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fnavigator%2Fregisterprotocolhandler%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F9b648e559239b3e682abfcb15845a954d420b207%0A*+Document+last+modified%3A+2021-05-31T17%3A00%3A38.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22Navigator.registerProtocolHandler%28%29%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/registerProtocolHandler/contributors.txt)

Change your languageSelect your preferred language English (US)DeutschEspañolFrançais日本語한국어PolskiРусский中文 (简体)正體中文 (繁體)

Change language

#### Related Topics

1.  **[`Navigator`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator)**
2.  Properties
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
3.  Methods
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
    12. *`registerProtocolHandler()`*
    13. [`requestMediaKeySystemAccess()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/requestMediaKeySystemAccess)
    14. [`sendBeacon()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/sendBeacon)
    15. [`setAppBadge()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/setAppBadge)
    16. [`share()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/share)
    17. [`taintEnabled()`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorID/taintEnabled)
    18. [`vibrate()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/vibrate)
    19. [`watchPosition()`](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation/watchPosition)
4.  Related pages for HTML DOM
    1.  [`BeforeUnloadEvent`](https://developer.mozilla.org/en-US/docs/Web/API/BeforeUnloadEvent)
    2.  [`DOMStringMap`](https://developer.mozilla.org/en-US/docs/Web/API/DOMStringMap)
    3.  [`ErrorEvent`](https://developer.mozilla.org/en-US/docs/Web/API/ErrorEvent)
    4.  [`GlobalEventHandlers`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers)
    5.  [`HTMLAnchorElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAnchorElement)
    6.  [`HTMLAreaElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement)
    7.  [`HTMLAudioElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAudioElement)
    8.  [`HTMLBRElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLBRElement)
    9.  [`HTMLBaseElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLBaseElement)
    10. [`HTMLBaseFontElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLBaseFontElement)
    11. [`HTMLBodyElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLBodyElement)
    12. [`HTMLButtonElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLButtonElement)
    13. [`HTMLCanvasElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement)
    14. [`HTMLContentElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLContentElement)
    15. [`HTMLDListElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDListElement)
    16. [`HTMLDataElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDataElement)
    17. [`HTMLDataListElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDataListElement)
    18. [`HTMLDialogElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDialogElement)
    19. [`HTMLDivElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDivElement)
    20. [`HTMLDocument`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDocument)
    21. [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
    22. [`HTMLEmbedElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLEmbedElement)
    23. [`HTMLFieldSetElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFieldSetElement)
    24. [`HTMLFormControlsCollection`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormControlsCollection)
    25. [`HTMLFormElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement)
    26. [`HTMLFrameSetElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFrameSetElement)
    27. [`HTMLHRElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLHRElement)
    28. [`HTMLHeadElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLHeadElement)
    29. [`HTMLHeadingElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLHeadingElement)
    30. [`HTMLHtmlElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLHtmlElement)
    31. [`HTMLIFrameElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLIFrameElement)
    32. [`HTMLImageElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement)
    33. [`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement)
    34. [`HTMLIsIndexElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLIsIndexElement)
    35. [`HTMLKeygenElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLKeygenElement)
    36. [`HTMLLIElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLLIElement)
    37. [`HTMLLabelElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLLabelElement)
    38. [`HTMLLegendElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLLegendElement)
    39. [`HTMLLinkElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLLinkElement)
    40. [`HTMLMapElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMapElement)
    41. [`HTMLMediaElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement)
    42. [`HTMLMetaElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMetaElement)
    43. [`HTMLMeterElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMeterElement)
    44. [`HTMLModElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLModElement)
    45. [`HTMLOListElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOListElement)
    46. [`HTMLObjectElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLObjectElement)
    47. [`HTMLOptGroupElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOptGroupElement)
    48. [`HTMLOptionElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOptionElement)
    49. [`HTMLOptionsCollection`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOptionsCollection)
    50. [`HTMLOutputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOutputElement)
    51. [`HTMLParagraphElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLParagraphElement)
    52. [`HTMLParamElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLParamElement)
    53. [`HTMLPictureElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLPictureElement)
    54. [`HTMLPreElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLPreElement)
    55. [`HTMLProgressElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLProgressElement)
    56. [`HTMLQuoteElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLQuoteElement)
    57. [`HTMLScriptElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLScriptElement)
    58. [`HTMLSelectElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement)
    59. [`HTMLShadowElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLShadowElement)
    60. [`HTMLSourceElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSourceElement)
    61. [`HTMLSpanElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSpanElement)
    62. [`HTMLStyleElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLStyleElement)
    63. [`HTMLTableCaptionElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableCaptionElement)
    64. [`HTMLTableCellElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableCellElement)
    65. [`HTMLTableColElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableColElement)
    66. [`HTMLTableDataCellElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableDataCellElement)
    67. [`HTMLTableElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableElement)
    68. [`HTMLTableHeaderCellElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableHeaderCellElement)
    69. [`HTMLTableRowElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableRowElement)
    70. [`HTMLTableSectionElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableSectionElement)
    71. [`HTMLTemplateElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTemplateElement)
    72. [`HTMLTextAreaElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTextAreaElement)
    73. [`HTMLTimeElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTimeElement)
    74. [`HTMLTitleElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTitleElement)
    75. [`HTMLTrackElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTrackElement)
    76. [`HTMLUListElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLUListElement)
    77. [`HTMLUnknownElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLUnknownElement)
    78. [`HTMLVideoElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLVideoElement)
    79. [`HashChangeEvent`](https://developer.mozilla.org/en-US/docs/Web/API/HashChangeEvent)
    80. [`History`](https://developer.mozilla.org/en-US/docs/Web/API/History)
    81. [`ImageData`](https://developer.mozilla.org/en-US/docs/Web/API/ImageData)
    82. [`Location`](https://developer.mozilla.org/en-US/docs/Web/API/Location)
    83. [`MessageChannel`](https://developer.mozilla.org/en-US/docs/Web/API/MessageChannel)
    84. [`MessageEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MessageEvent)
    85. [`MessagePort`](https://developer.mozilla.org/en-US/docs/Web/API/MessagePort)
    86. [`NavigatorGeolocation`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorGeolocation)
    87. [`NavigatorID`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorID)
    88. [`NavigatorLanguage`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorLanguage)
    89. [`NavigatorOnLine`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorOnLine)
    90. [`NavigatorPlugins`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorPlugins)
    91. [`PageTransitionEvent`](https://developer.mozilla.org/en-US/docs/Web/API/PageTransitionEvent)
    92. [`Plugin`](https://developer.mozilla.org/en-US/docs/Web/API/Plugin)
    93. [`PluginArray`](https://developer.mozilla.org/en-US/docs/Web/API/PluginArray)
    94. [`PopStateEvent`](https://developer.mozilla.org/en-US/docs/Web/API/PopStateEvent)
    95. [`PortCollection`](https://developer.mozilla.org/en-US/docs/Web/API/PortCollection)
    96. [`PromiseRejectionEvent`](https://developer.mozilla.org/en-US/docs/Web/API/PromiseRejectionEvent)
    97. [`RadioNodeList`](https://developer.mozilla.org/en-US/docs/Web/API/RadioNodeList)
    98. [`Transferable`](https://developer.mozilla.org/en-US/docs/Web/API/Transferable)
    99. [`ValidityState`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState)
    100. [`Window`](https://developer.mozilla.org/en-US/docs/Web/API/Window)
    101. [`WindowBase64`](https://developer.mozilla.org/en-US/docs/Web/API/WindowBase64)
    102. [`WindowEventHandlers`](https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers)
    103. [`WindowTimers`](https://developer.mozilla.org/en-US/docs/Web/API/WindowTimers)

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
