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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints" class="breadcrumb-current-page"><span data-property="name">MediaTrackSupportedConstraints</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Properties](#properties)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

MediaTrackSupportedConstraints
==============================

The **`MediaTrackSupportedConstraints`** dictionary establishes the list of constrainable properties recognized by the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) or browser in its implementation of the [`MediaStreamTrack`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack) object. An object conforming to `MediaTrackSupportedConstraints` is returned by [`MediaDevices.getSupportedConstraints()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getSupportedConstraints).

Because of the way interface definitions in WebIDL work, if a constraint is requested but not supported, no error will occur. Instead, the specified constraints will be applied, with any unrecognized constraints stripped from the request.That can lead to confusing and hard to debug errors, so be sure to use `getSupportedConstraints()` to retrieve this information before attempting to establish constraints if you need to know the difference between silently ignoring a constraint and a constraint being accepted.

An actual constraint set is described using an object based on the [`MediaTrackConstraints`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackConstraints) dictionary.

To learn more about how constraints work, see [Capabilities, constraints, and settings](https://developer.mozilla.org/en-US/docs/Web/API/Media_Streams_API/Constraints).

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

Some combination—but not necessarily all—of the following properties will exist on the object.

[`autoGainControl`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints/autoGainControl "autoGainControl")  
A Boolean whose value is `true` if the `autoGainControl` constraint is supported in the current environment.

[`width`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints/width "width")  
A Boolean value whose value is `true` if the `width` constraint is supported in the current environment.

[`height`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints/height "height")  
A Boolean value whose value is `true` if the `height` constraint is supported in the current environment.

[`aspectRatio`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints/aspectRatio "aspectRatio")  
A Boolean value whose value is `true` if the `aspectRatio` constraint is supported in the current environment.

[`frameRate`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints/frameRate "frameRate")  
A Boolean value whose value is `true` if the `frameRate` constraint is supported in the current environment.

[`facingMode`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints/facingMode "facingMode")  
A Boolean value whose value is `true` if the `facingMode` constraint is supported in the current environment.

<span class="page-not-created">`resizeMode`</span>  
A Boolean value whose value is `true` if the `resizeMode` constraint is supported in the current environment.

[`volume`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints/volume "volume")  
A Boolean value whose value is `true` if the `volume` constraint is supported in the current environment.

[`sampleRate`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints/sampleRate "sampleRate")  
A Boolean value whose value is `true` if the `sampleRate` constraint is supported in the current environment.

[`sampleSize`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints/sampleSize "sampleSize")  
A Boolean value whose value is `true` if the `sampleSize` constraint is supported in the current environment.

[`echoCancellation`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints/echoCancellation "echoCancellation")  
A Boolean value whose value is `true` if the `echoCancellation` constraint is supported in the current environment.

[`latency`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints/latency "latency")  
A Boolean value whose value is `true` if the `latency` constraint is supported in the current environment.

[`noiseSuppression`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints/noiseSuppression "noiseSuppression")  
A Boolean whose value is `true` if the `noiseSuppression` constraint is supported in the current environment.

[`channelCount`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints/channelCount "channelCount")  
A Boolean value whose value is `true` if the `channelCount` constraint is supported in the current environment.

[`deviceId`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints/deviceId "deviceId")  
A Boolean value whose value is `true` if the `deviceId` constraint is supported in the current environment.

[`groupId`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints/groupId "groupId")  
A Boolean value whose value is `true` if the `groupId` constraint is supported in the current environment.

### [Properties specific to shared screen tracks](#properties_specific_to_shared_screen_tracks "Permalink to Properties specific to shared screen tracks")

For tracks containing video sources from the user's screen contents, the following additional properties are may be included in addition to those available for video tracks.

[`cursor`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints/cursor "cursor")  
A Boolean value which is `true` if the [`cursor`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackConstraints/cursor "cursor") constraint is supported in the current environment.

[`displaySurface`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints/displaySurface "displaySurface")  
A Boolean value which is `true` if the [`cursor`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackConstraints/displaySurface "cursor") constraint is supported in the current environment.

[`logicalSurface`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints/logicalSurface "logicalSurface")  
A Boolean value which is `true` if the [`logicalSurface`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackConstraints/logicalSurface "logicalSurface") constraint is supported in the current environment.

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Media Capture and Streams API](https://developer.mozilla.org/en-US/docs/Web/API/Media_Streams_API)
-   [Capabilities, constraints, and settings](https://developer.mozilla.org/en-US/docs/Web/API/Media_Streams_API/Constraints)
-   [Screen Capture API](https://developer.mozilla.org/en-US/docs/Web/API/Screen_Capture_API)
-   [Using the Screen Capture API](https://developer.mozilla.org/en-US/docs/Web/API/Screen_Capture_API/Using_Screen_Capture)
-   [`MediaTrackConstraints`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackConstraints)
-   [`MediaDevices.getUserMedia()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getUserMedia)
-   [`MediaStreamTrack.getConstraints()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/getConstraints)
-   [`MediaStreamTrack.applyConstraints()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/applyConstraints)
-   [`MediaStreamTrack.getSettings()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/getSettings)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/mediatracksupportedconstraints/index.html "Folder: en-us/web/api/mediatracksupportedconstraints (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FMediaTrackSupportedConstraints%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fmediatracksupportedconstraints%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FMediaTrackSupportedConstraints%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fmediatracksupportedconstraints%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F5737ba49f3f0c3fc7587d329f1362a7a66afdd80%0A*+Document+last+modified%3A+2021-05-31T16%3A58%3A42.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22MediaTrackSupportedConstraints%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints/contributors.txt)

Change your languageSelect your preferred language English (US)日本語

Change language

#### Related Topics

1.  **[Media Streams API](https://developer.mozilla.org/en-US/docs/Web/API/Media_Streams_API)**
2.  **[`MediaTrackSupportedConstraints`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints)**
3.  Properties
    1.  [`aspectRatio`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints/aspectRatio)
    2.  [`autoGainControl`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints/autoGainControl)
    3.  [`channelCount`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints/channelCount)
    4.  [`cursor`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints/cursor)
    5.  [`deviceId`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints/deviceId)
    6.  [`displaySurface`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints/displaySurface)
    7.  [`echoCancellation`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints/echoCancellation)
    8.  [`facingMode`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints/facingMode)
    9.  [`frameRate`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints/frameRate)
    10. [`groupId`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints/groupId)
    11. [`height`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints/height)
    12. [`latency`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints/latency)
    13. [`noiseSuppression`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints/noiseSuppression)
    14. [`sampleRate`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints/sampleRate)
    15. [`sampleSize`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints/sampleSize)
    16. [`volume`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints/volume)
4.  Related pages for Media Capture and Streams
    1.  [`AudioStreamTrack`](https://developer.mozilla.org/en-US/docs/Web/API/AudioStreamTrack)
    2.  [`BlobEvent`](https://developer.mozilla.org/en-US/docs/Web/API/BlobEvent)
    3.  [`CanvasCaptureMediaStream`](https://developer.mozilla.org/en-US/docs/Web/API/CanvasCaptureMediaStream)
    4.  [`ConstrainBoolean`](https://developer.mozilla.org/en-US/docs/Web/API/ConstrainBoolean)
    5.  [`ConstrainDOMString`](https://developer.mozilla.org/en-US/docs/Web/API/ConstrainDOMString)
    6.  [`ConstrainDouble`](https://developer.mozilla.org/en-US/docs/Web/API/ConstrainDouble)
    7.  [`ConstrainLong`](https://developer.mozilla.org/en-US/docs/Web/API/ConstrainLong)
    8.  [`DoubleRange`](https://developer.mozilla.org/en-US/docs/Web/API/DoubleRange)
    9.  [`HTMLCanvasElement.captureStream()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/captureStream)
    10. [`LongRange`](https://developer.mozilla.org/en-US/docs/Web/API/LongRange)
    11. [`MediaDevices`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices)
    12. [`MediaStream`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream)
    13. [`MediaStreamTrack`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack)
    14. [`MediaStreamTrackEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrackEvent)
    15. [`MediaTrackCapabilities`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackCapabilities)
    16. [`MediaTrackConstraints`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackConstraints)
    17. [`MediaTrackSettings`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings)
    18. [`Navigator.mediaDevices`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/mediaDevices)
    19. [`NavigatorUserMedia`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorUserMedia)
    20. [`NavigatorUserMediaError`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorUserMediaError)
    21. [`VideoStreamTrack`](https://developer.mozilla.org/en-US/docs/Web/API/VideoStreamTrack)
    22. [`navigator.mediaDevices.getUserMedia()`](https://developer.mozilla.org/en-US/docs/Web/API/navigator/mediaDevices.getUserMedia)

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
