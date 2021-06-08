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
3.  <a href="../Navigator.html" class="breadcrumb-penultimate"><span data-property="name">Navigator</span></a>
4.  <a href="getUserMedia.html" class="breadcrumb-current-page"><span data-property="name">Navigator.getUserMedia()</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Syntax](#syntax)
-   [Examples](#examples)
-   [Permissions](#permissions)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

Navigator.getUserMedia()
========================

#### Deprecated

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The deprecated `Navigator.getUserMedia()` method prompts the user for permission to use up to one video input device (such as a camera or shared screen) and up to one audio input device (such as a microphone) as the source for a [`MediaStream`](../MediaStream.html).

If permission is granted, a `MediaStream` whose video and/or audio tracks come from those devices is delivered to the specified success callback. If permission is denied, no compatible input devices exist, or any other error condition occurs, the error callback is executed with a <span class="page-not-created">`MediaStreamError`</span> object describing what went wrong. If the user instead doesn't make a choice at all, neither callback is executed.

This is a legacy method. Please use the newer [`navigator.mediaDevices.getUserMedia()`](../MediaDevices/getUserMedia.html "navigator.mediaDevices.getUserMedia()") instead. While technically not deprecated, this old callback version is marked as such, since the specification strongly encourages using the newer promise returning version.

[Syntax](#syntax "Permalink to Syntax")
---------------------------------------

    navigator.getUserMedia(constraints, successCallback, errorCallback);

### [Parameters](#parameters "Permalink to Parameters")

`constraints`  
A [`MediaStreamConstraints`](../MediaStreamConstraints.html) object specifying the types of media to request, along with any requirements for each type. For details, see the [constraints](../MediaDevices/getUserMedia.html#parameters) section under the modern [`MediaDevices.getUserMedia()`](../MediaDevices/getUserMedia.html) method, as well as the article [Capabilities, constraints, and settings](../Media_Streams_API/Constraints.html).

`successCallback`  
A function which is invoked when the request for media access is approved. The function is called with one parameter: the [`MediaStream`](../MediaStream.html) object that contains the media stream. Your callback can then assign the stream to the desired object (such as an [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) or [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element), as shown in the following example:

    function(stream) {
       var video = document.querySelector('video');
       video.srcObject = stream;
       video.onloadedmetadata = function(e) {
          // Do something with the video here.
       };
    }

`errorCallback`  
When the call fails, the function specified in the `errorCallback` is invokedwith a <span class="page-not-created">`MediaStreamError`</span> object as its sole argument; this object is modeled on [`DOMException`](../DOMException.html). See [Errors](#errors) below for a list of the errors which can occur.

### [Return value](#return_value "Permalink to Return value")

<span class="page-not-created">`undefined`</span>.

[Examples](#examples "Permalink to Examples")
---------------------------------------------

### [Width and height](#width_and_height "Permalink to Width and height")

Here's an example of using `getUserMedia()`, including code to cope with various browsers' prefixes. Note that this is the deprecated way of doing it: See the [Examples](../MediaDevices/getUserMedia.html#frame_rate) section under the [`MediaDevices.getUserMedia()`](../MediaDevices/getUserMedia.html) for modern examples.

    navigator.getUserMedia = navigator.getUserMedia ||
                             navigator.webkitGetUserMedia ||
                             navigator.mozGetUserMedia;

    if (navigator.getUserMedia) {
       navigator.getUserMedia({ audio: true, video: { width: 1280, height: 720 } },
          function(stream) {
             var video = document.querySelector('video');
             video.srcObject = stream;
             video.onloadedmetadata = function(e) {
               video.play();
             };
          },
          function(err) {
             console.log("The following error occurred: " + err.name);
          }
       );
    } else {
       console.log("getUserMedia not supported");
    }

[Permissions](#permissions "Permalink to Permissions")
------------------------------------------------------

To use `getUserMedia()` in an installable app (for example, a [Firefox OS app](https://developer.mozilla.org/en-US/docs/Web/Apps/Build/Building_apps_for_Firefox_OS/Firefox_OS_app_beginners_tutorial)), you need to specify one or both of the following fields inside your manifest file:

    "permissions": {
      "audio-capture": {
        "description": "Required to capture audio using getUserMedia()"
      },
      "video-capture": {
        "description": "Required to capture video using getUserMedia()"
      }
    }

See [permission: audio-capture](https://developer.mozilla.org/en-US/docs/Web/Apps/Developing/App_permissions#audio-capture) and [permission: video-capture](https://developer.mozilla.org/en-US/docs/Web/Apps/Developing/App_permissions#video-capture) for more information.

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

New code should use [`Navigator.mediaDevices.getUserMedia()`](../MediaDevices/getUserMedia.html) instead.

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [`MediaDevices.getUserMedia()`](../MediaDevices/getUserMedia.html) that replaces this deprecated method.
-   [WebRTC](../WebRTC_API.html) - the introductory page to the API
-   [MediaStream API](../Media_Streams_API.html) - the API for the media stream objects
-   [Taking webcam photos](../WebRTC_API/Taking_still_photos.html) - a tutorial on using `getUserMedia() for taking photos rather than video.`

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/navigator/getusermedia/index.html "Folder: en-us/web/api/navigator/getusermedia (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FNavigator%2FgetUserMedia%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fnavigator%2Fgetusermedia%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FNavigator%2FgetUserMedia%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fnavigator%2Fgetusermedia%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F9b648e559239b3e682abfcb15845a954d420b207%0A*+Document+last+modified%3A+2021-05-31T17%3A00%3A38.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22Navigator.getUserMedia%28%29%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](getUserMedia/contributors.txt)

Change your languageSelect your preferred language English (US)EspañolFrançais日本語Português (do Brasil)Русский中文 (简体)

Change language

#### Related Topics

1.  **[Media Streams API](../Media_Streams_API.html)**
2.  **[`Navigator`](../Navigator.html)**
3.  Properties
    1.  [`activeVRDisplays`](activeVRDisplays.html)
    2.  [`appCodeName`](../NavigatorID/appCodeName.html)
    3.  [`appName`](../NavigatorID/appName.html)
    4.  [`appVersion`](../NavigatorID/appVersion.html)
    5.  [`battery`](battery.html)
    6.  [`buildID`](buildID.html)
    7.  [`clipboard`](clipboard.html)
    8.  [`connection`](connection.html)
    9.  [`contacts`](contacts.html)
    10. [`cookieEnabled`](cookieEnabled.html)
    11. [`credentials`](credentials.html)
    12. [`deviceMemory`](deviceMemory.html)
    13. [`doNotTrack`](doNotTrack.html)
    14. [`geolocation`](geolocation.html)
    15. [`hid`](hid.html)
    16. [`keyboard`](keyboard.html)
    17. [`language`](../NavigatorLanguage/language.html)
    18. [`languages`](../NavigatorLanguage/languages.html)
    19. [`locks`](locks.html)
    20. [`maxTouchPoints`](maxTouchPoints.html)
    21. [`mediaDevices`](mediaDevices.html)
    22. [`mediaSession`](mediaSession.html)
    23. [`onLine`](../NavigatorOnLine/onLine.html)
    24. [`oscpu`](oscpu.html)
    25. [`permissions`](permissions.html)
    26. [`platform`](../NavigatorID/platform.html)
    27. [`product`](../NavigatorID/product.html)
    28. [`productSub`](productSub.html)
    29. [`serial`](serial.html)
    30. [`serviceWorker`](serviceWorker.html)
    31. [`userAgent`](../NavigatorID/userAgent.html)
    32. [`vendor`](vendor.html)
    33. [`vendorSub`](vendorSub.html)
    34. [`webdriver`](webdriver.html)
    35. [`xr`](xr.html)
4.  Methods
    1.  [`canShare()`](canShare.html)
    2.  [`clearAppBadge()`](clearAppBadge.html)
    3.  [`clearWatch()`](../Geolocation/clearWatch.html)
    4.  [`getBattery()`](getBattery.html)
    5.  [`getCurrentPosition()`](../Geolocation/getCurrentPosition.html)
    6.  [`getGamepads()`](getGamepads.html)
    7.  *`getUserMedia()`*
    8.  [`getVRDisplays()`](getVRDisplays.html)
    9.  [`mozIsLocallyAvailable()`](mozIsLocallyAvailable.html)
    10. [`msLaunchUri()`](msLaunchUri.html)
    11. [`registerContentHandler()`](registerContentHandler.html)
    12. [`registerProtocolHandler()`](registerProtocolHandler.html)
    13. [`requestMediaKeySystemAccess()`](requestMediaKeySystemAccess.html)
    14. [`sendBeacon()`](sendBeacon.html)
    15. [`setAppBadge()`](setAppBadge.html)
    16. [`share()`](share.html)
    17. [`taintEnabled()`](../NavigatorID/taintEnabled.html)
    18. [`vibrate()`](vibrate.html)
    19. [`watchPosition()`](../Geolocation/watchPosition.html)
5.  Related pages for Media Capture and Streams
    1.  [`AudioStreamTrack`](../AudioStreamTrack.html)
    2.  [`BlobEvent`](../BlobEvent.html)
    3.  [`CanvasCaptureMediaStream`](../CanvasCaptureMediaStreamTrack.html)
    4.  [`ConstrainBoolean`](../ConstrainBoolean.html)
    5.  [`ConstrainDOMString`](../ConstrainDOMString.html)
    6.  [`ConstrainDouble`](../ConstrainDouble.html)
    7.  [`ConstrainLong`](../ConstrainULong.html)
    8.  [`DoubleRange`](../DoubleRange.html)
    9.  [`HTMLCanvasElement.captureStream()`](../HTMLCanvasElement/captureStream.html)
    10. [`LongRange`](../ULongRange.html)
    11. [`MediaDevices`](../MediaDevices.html)
    12. [`MediaStream`](../MediaStream.html)
    13. [`MediaStreamTrack`](../MediaStreamTrack.html)
    14. [`MediaStreamTrackEvent`](../MediaStreamTrackEvent.html)
    15. [`MediaTrackCapabilities`](../MediaTrackCapabilities.html)
    16. [`MediaTrackConstraints`](../MediaTrackConstraints.html)
    17. [`MediaTrackSettings`](../MediaTrackSettings.html)
    18. [`MediaTrackSupportedConstraints`](../MediaTrackSupportedConstraints.html)
    19. [`Navigator.mediaDevices`](mediaDevices.html)
    20. [`NavigatorUserMedia`](../NavigatorUserMedia.html)
    21. [`NavigatorUserMediaError`](../NavigatorUserMediaError.html)
    22. [`VideoStreamTrack`](../VideoStreamTrack.html)
    23. [`navigator.mediaDevices.getUserMedia()`](../MediaDevices/getUserMedia.html)

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
