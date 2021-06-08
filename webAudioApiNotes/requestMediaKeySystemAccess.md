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
4.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/Navigator/requestMediaKeySystemAccess" class="breadcrumb-current-page"><span data-property="name">Navigator.requestMediaKeySystemAccess()</span></a>

Table of contents
-----------------

Table of contents

-   [Syntax](#syntax)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

Navigator.requestMediaKeySystemAccess()
=======================================

The **`Navigator.requestMediaKeySystemAccess()`** method returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which delivers a [`MediaKeySystemAccess`](https://developer.mozilla.org/en-US/docs/Web/API/MediaKeySystemAccess) object that can be used to access a particular media key system, which can in turn be used to create keys for decrypting a media stream. This method is part of the [Encrypted Media Extensions API](https://developer.mozilla.org/en-US/docs/Web/API/Encrypted_Media_Extensions_API), which brings support for encrypted media and DRM-protected video to the web.

This method may have user-visible effects such as asking for permission to access one or more system resources. Consider that when deciding when to call `requestMediaKeySystemAccess``()`; you don't want those requests to happen at inconvenient times. As a general rule, this function should be called only when it's about time to create and use a [`MediaKeys`](https://developer.mozilla.org/en-US/docs/Web/API/MediaKeys) object by calling the returned [`MediaKeySystemAccess`](https://developer.mozilla.org/en-US/docs/Web/API/MediaKeySystemAccess) object's [`createMediaKeys()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaKeySystemAccess/createMediaKeys "createMediaKeys()") method.

[Syntax](#syntax "Permalink to Syntax")
---------------------------------------

    promise = navigator.requestMediaKeySystemAccess(keySystem, supportedConfigurations);

### [Parameters](#parameters "Permalink to Parameters")

`keySystem`  
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) identifying the key system. For example `com.example.somesystem` or `org.w3.clearkey`.

`supportedConfigurations`  
A non-empty [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of [`MediaKeySystemConfiguration`](https://developer.mozilla.org/en-US/docs/Web/API/MediaKeySystemConfiguration) objects. The first element with a satisfiable configuration will be used.

### [Return value](#return_value "Permalink to Return value")

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that, when resolved, delivers a [`MediaKeySystemAccess`](https://developer.mozilla.org/en-US/docs/Web/API/MediaKeySystemAccess) object to your fulfillment handler function. The fulfillment handler receives as input just one parameter:

`mediaKeySystemAccess`  
A [`MediaKeySystemAccess`](https://developer.mozilla.org/en-US/docs/Web/API/MediaKeySystemAccess) object representing the media key system configuration described by `keySystem` and `supportedConfigurations`

### [Exceptions](#exceptions "Permalink to Exceptions")

In case of an error, the returned [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) is rejected with a [`DOMException`](https://developer.mozilla.org/en-US/docs/Web/API/DOMException) whose name indicates what kind of error occurred.

`NotSupportedError`  
Either the specified `keySystem` isn't supported by the platform or the browser, or none of the configurations specified by `supportedConfigurations` can be satisfied (if, for example, none of the `codecs` specified in `contentType` are available).

`TypeError`  
Either `keySystem` is an empty string or the `supportedConfigurations` array is empty.

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/encrypted-media/#navigator-extension-requestmediakeysystemaccess" class="external">Encrypted Media Extensions<br />
<span class="small">The definition of 'requestMediaKeySystemAccess()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

### [Firefox compatibility notes](#firefox_compatibility_notes "Permalink to Firefox compatibility notes")

Firefox 55 outputs a warning to the console if a candidate [`MediaKeySystemConfiguration`](https://developer.mozilla.org/en-US/docs/Web/API/MediaKeySystemConfiguration) included in `supportedConfigurations` includes an `audioCapabilities` or `videoCapabilities` object whose value of `contentType` doesn't specify a `"codecs"` substring defining which codecs within the media wrapper format should be allowed.

For example:

    let clearKeyOptions = [
      {
        initDataTypes: ['keyids', 'webm'],
        audioCapabilities: [
          { contentType: 'audio/webm' }
        ],
        videoCapabilities: [
          { contentType: 'video/webm' }
        ]
      }
    ];

    navigator.requestMediaKeySystemAccess('org.w3.clearkey', clearKeyOptions)
    .then(function(keySystemAccess) {
      /* use the access to get create keys */
    });

The code above works in Firefox up to version 55, but version 55 onwards will output a warning to console, because `"codecs"` is not included in the `contentType` strings. This could be corrected as follows:

    let clearKeyOptions = [
      {
        initDataTypes: ['keyids', 'webm'],
        audioCapabilities: [
          { contentType: 'audio/webm; codecs="opus"' },
          { contentType: 'audio/webm; codecs="vorbis"' }
        ],
        videoCapabilities: [
          { contentType: 'video/webm; codecs="vp9"' },
          { contentType: 'video/webm; codecs="vp8"' }
        ]
      }
    ];

    navigator.requestMediaKeySystemAccess('org.w3.clearkey', clearKeyOptions)
    .then(function(keySystemAccess) {
      /* use the access to get create keys */
    });

In this revised example, the audio and video capabilities include possible codecs which should be permitted, and therefore are valid requests.

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Encrypted Media Extensions API](https://developer.mozilla.org/en-US/docs/Web/API/Encrypted_Media_Extensions_API)
-   [Media Capture and Streams API](https://developer.mozilla.org/en-US/docs/Web/API/Media_Streams_API)
-   [WebRTC API](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/navigator/requestmediakeysystemaccess/index.html "Folder: en-us/web/api/navigator/requestmediakeysystemaccess (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FNavigator%2FrequestMediaKeySystemAccess%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fnavigator%2Frequestmediakeysystemaccess%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FNavigator%2FrequestMediaKeySystemAccess%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fnavigator%2Frequestmediakeysystemaccess%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F9b648e559239b3e682abfcb15845a954d420b207%0A*+Document+last+modified%3A+2021-05-31T17%3A00%3A38.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22Navigator.requestMediaKeySystemAccess%28%29%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/requestMediaKeySystemAccess/contributors.txt)

#### Related Topics

1.  **[Encrypted Media Extensions API](https://developer.mozilla.org/en-US/docs/Web/API/Encrypted_Media_Extensions_API)**
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
    13. *`requestMediaKeySystemAccess()`*
    14. [`sendBeacon()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/sendBeacon)
    15. [`setAppBadge()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/setAppBadge)
    16. [`share()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/share)
    17. [`taintEnabled()`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorID/taintEnabled)
    18. [`vibrate()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/vibrate)
    19. [`watchPosition()`](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation/watchPosition)
5.  Related pages for Encrypted Media Extensions
    1.  [`HTMLMediaElement.mediaKeys`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/mediaKeys)
    2.  [`HTMLMediaElement.onencrypted`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/onencrypted)
    3.  [`HTMLMediaElement.setMediaKeys()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/setMediaKeys)
    4.  [`MediaKeySession`](https://developer.mozilla.org/en-US/docs/Web/API/MediaKeySession)
    5.  [`MediaKeySessionEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MediaKeySessionEvent)
    6.  [`MediaKeyStatusMap`](https://developer.mozilla.org/en-US/docs/Web/API/MediaKeyStatusMap)
    7.  [`MediaKeySystemAccess`](https://developer.mozilla.org/en-US/docs/Web/API/MediaKeySystemAccess)
    8.  [`MediaKeySystemConfiguration`](https://developer.mozilla.org/en-US/docs/Web/API/MediaKeySystemConfiguration)
    9.  [`MediaKeys`](https://developer.mozilla.org/en-US/docs/Web/API/MediaKeys)
    10. [`Navigator.requestMediaKeySystemAccess()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/requestMediaKeySystemAccess)

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
