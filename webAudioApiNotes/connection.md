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
4.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/Navigator/connection" class="breadcrumb-current-page"><span data-property="name">Navigator.connection</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Syntax](#syntax)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

Navigator.connection
====================

#### Experimental

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

<span class="seoSummary">The `Navigator.connection` read-only property returns a [`NetworkInformation`](https://developer.mozilla.org/en-US/docs/Web/API/NetworkInformation) object containing information about the system's connection, such as the current bandwidth of the user's device or whether the connection is metered.</span> This could be used to select high definition content or low definition content based on the user's connection.

[Syntax](#syntax "Permalink to Syntax")
---------------------------------------

    var networkInformation = navigator.connection

### [Value](#value "Permalink to Value")

A [`NetworkInformation`](https://developer.mozilla.org/en-US/docs/Web/API/NetworkInformation) object.

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/netinfo/#connection-attribute" class="external">Network Information API<br />
<span class="small">The definition of 'Navigator.connection' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial specification</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Online and offline events](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorOnLine/Online_and_offline_events)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/navigator/connection/index.html "Folder: en-us/web/api/navigator/connection (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FNavigator%2Fconnection%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fnavigator%2Fconnection%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FNavigator%2Fconnection%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fnavigator%2Fconnection%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F9b648e559239b3e682abfcb15845a954d420b207%0A*+Document+last+modified%3A+2021-05-31T17%3A00%3A38.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22Navigator.connection%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/connection/contributors.txt)

Change your languageSelect your preferred language English (US)Français日本語한국어Русский中文 (简体)

Change language

#### Related Topics

1.  **[Network Information API](https://developer.mozilla.org/en-US/docs/Web/API/Network_Information_API)**
2.  **[`Navigator`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator)**
3.  Properties
    1.  [`activeVRDisplays`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/activeVRDisplays)
    2.  [`appCodeName`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorID/appCodeName)
    3.  [`appName`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorID/appName)
    4.  [`appVersion`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorID/appVersion)
    5.  [`battery`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/battery)
    6.  [`buildID`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/buildID)
    7.  [`clipboard`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/clipboard)
    8.  *`connection`*
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
5.  Related pages for Network Information API
    1.  [`Navigator.connection`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/connection)
    2.  [`NetworkInformation`](https://developer.mozilla.org/en-US/docs/Web/API/NetworkInformation)

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
