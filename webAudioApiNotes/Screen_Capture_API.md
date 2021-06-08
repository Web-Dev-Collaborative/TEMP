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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/Screen_Capture_API" class="breadcrumb-current-page"><span data-property="name">Screen Capture API</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Screen Capture API concepts and usage](#screen_capture_api_concepts_and_usage)
-   [Additions to existing interfaces](#additions_to_existing_interfaces)
-   [Additions to existing dictionaries](#additions_to_existing_dictionaries)
-   [Dictionaries](#dictionaries)
-   [Feature Policy validation](#feature_policy_validation)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

Screen Capture API
==================

<span class="seoSummary">The Screen Capture API introduces additions to the existing Media Capture and Streams API to let the user select a screen or portion of a screen (such as a window) to capture as a media stream.</span> This stream can then be recorded or shared with others over the network.

[Screen Capture API concepts and usage](#screen_capture_api_concepts_and_usage "Permalink to Screen Capture API concepts and usage")
------------------------------------------------------------------------------------------------------------------------------------

The Screen Capture API is relatively simple to use. Its sole method is [`MediaDevices.getDisplayMedia()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getDisplayMedia), whose job is to ask the user to select a screen or portion of a screen to capture in the form of a [`MediaStream`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream).

To start capturing video from the screen, you call `getDisplayMedia()` on the instance of `Media` `navigator.mediaDevices`:

    captureStream = await navigator.mediaDevices.getDisplayMedia(displayMediaOptions);

The [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) returned by `getDisplayMedia()` resolves to a [`MediaStream`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream) which streams the captured media.

See the article [Using the Screen Capture API](https://developer.mozilla.org/en-US/docs/Web/API/Screen_Capture_API/Using_Screen_Capture) for a more in-depth look at how to use the API to capture screen contents as a stream.

[Additions to existing interfaces](#additions_to_existing_interfaces "Permalink to Additions to existing interfaces")
---------------------------------------------------------------------------------------------------------------------

The Screen Capture API doesn't have any interfaces of its own; instead, it adds one method to the existing [`MediaDevices`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices) interface.

### [MediaDevices interface](#mediadevices_interface "Permalink to MediaDevices interface")

[`MediaDevices.getDisplayMedia()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getDisplayMedia)  
The `getDisplayMedia()` method is added to the `MediaDevices` interface. Similar to [`getUserMedia()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getUserMedia "getUserMedia()"), this method creates a promise that resolves with a [`MediaStream`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream) containing the display area selected by the user, in a format that matches the specified options.

[Additions to existing dictionaries](#additions_to_existing_dictionaries "Permalink to Additions to existing dictionaries")
---------------------------------------------------------------------------------------------------------------------------

The Screen Capture API adds properties to the following dictionaries defined by other specifications.

### [MediaTrackConstraints](#mediatrackconstraints "Permalink to MediaTrackConstraints")

[`MediaTrackConstraints.cursor`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackConstraints/cursor)  
A [`ConstrainDOMString`](https://developer.mozilla.org/en-US/docs/Web/API/ConstrainDOMString) indicating whether or not the cursor should be included in the captured display surface's stream, and if it should always be visible or if it should only be visible while the mouse is in motion.

[`MediaTrackConstraints.displaySurface`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackConstraints/displaySurface)  
A [`ConstrainDOMString`](https://developer.mozilla.org/en-US/docs/Web/API/ConstrainDOMString) indicating what type of display surface is to be captured. The value is one of `application`, `browser`, `monitor`, or `window`.

[`MediaTrackConstraints.logicalSurface`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackConstraints/logicalSurface)  
Indicates whether or not the video in the stream represents a logical display surface (that is, one which may not be entirely visible onscreen, or may be completely offscreen). A value of `true` indicates a logical display surface is to be captured.

### [MediaTrackSettings](#mediatracksettings "Permalink to MediaTrackSettings")

[`MediaTrackSettings.cursor`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/cursor)  
A string which indicates whether or not the display surface currently being captured includes the mouse cursor, and if so, whether it's only visible while the mouse is in motion or if it's always visible. The value is one of `always`, `motion`, or `never`.

[`MediaTrackSettings.displaySurface`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/displaySurface)  
A string indicating what type of display surface is currently being captured. The value is one of `application`, `browser`, `monitor`, or `window`.

[`MediaTrackSettings.logicalSurface`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/logicalSurface)  
A Boolean value which is `true` if the video being captured doesn't directly correspond to a single onscreen display area.

### [MediaTrackSupportedConstraints](#mediatracksupportedconstraints "Permalink to MediaTrackSupportedConstraints")

[`MediaTrackSupportedConstraints.cursor`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints/cursor)  
A Boolean which is `true` if the user agent and device support the [`MediaTrackConstraints.cursor`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackConstraints/cursor) constraint.

[`MediaTrackSupportedConstraints.displaySurface`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints/displaySurface)  
A Boolean which is `true` if the current environment supports the [`MediaTrackConstraints.displaySurface`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackConstraints/displaySurface) constraint.

[`MediaTrackSupportedConstraints.logicalSurface`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints/logicalSurface)  
A Boolean which is `true` if the current environment supports the constraint [`MediaTrackConstraints.logicalSurface`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackConstraints/logicalSurface).

[Dictionaries](#dictionaries "Permalink to Dictionaries")
---------------------------------------------------------

The following dictionaries are defined by the Screen Capture API.

`CursorCaptureConstraint`  
An enumerated string type used to provide the value for the `cursor` property for the settings and constraints. The possible values are `always`, `motion`, and `never`.

`DisplayCaptureSurfaceType`  
An enumerated string type which is used to identify the kind of display surface to capture. This type is used for the `displaySurface` property in the constraints and settings objects, and has the possible values `application`, `browser`, `monitor`, and `window`.

[Feature Policy validation](#feature_policy_validation "Permalink to Feature Policy validation")
------------------------------------------------------------------------------------------------

[User agents](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) that support Feature Policy (either using HTTP's [`Feature-Policy`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy) header or the [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) attribute [`allow`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe#attr-allow)) can specify a desire to use the Screen Capture API using the policy control directive `display-capture`:

    <iframe allow="display-capture" src="/some-other-document.html">

The default allow list is `self`, which lets the any content within the document use Screen Capture.

See [Using Feature Policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/Feature_Policy/Using_Feature_Policy) for a more in-depth explanation of how Feature Policy is used.

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-screen-share/" class="external" title="The &#39;Screen Capture&#39; specification">Screen Capture</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Using the Screen Capture API](https://developer.mozilla.org/en-US/docs/Web/API/Screen_Capture_API/Using_Screen_Capture)
-   [`MediaDevices.getDisplayMedia()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getDisplayMedia)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/screen_capture_api/index.html "Folder: en-us/web/api/screen_capture_api (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FScreen_Capture_API%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fscreen_capture_api%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FScreen_Capture_API%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fscreen_capture_api%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F63c69f3c933acbea9bfb24d359a7d2ffdb3c0bea%0A*+Document+last+modified%3A+2021-02-19T19%3A51%3A22.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22Screen+Capture+API%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Feb 19, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/Screen_Capture_API/contributors.txt)

Change your languageSelect your preferred language English (US)FrançaisРусский中文 (简体)

Change language

#### Related Topics

1.  **[Screen Capture API](https://developer.mozilla.org/en-US/docs/Web/API/Screen_Capture_API)**
2.  Guides
    1.  [Using the Screen Capture API](https://developer.mozilla.org/en-US/docs/Web/API/Screen_Capture_API/Using_Screen_Capture)
3.  Properties
    1.  [`MediaTrackConstraints.cursor`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackConstraints/cursor)
    2.  [`MediaTrackConstraints.displaySurface`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackConstraints/displaySurface)
    3.  [`MediaTrackConstraints.logicalSurface`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackConstraints/logicalSurface)
    4.  [`MediaTrackSettings.cursor`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/cursor)
    5.  [`MediaTrackSettings.displaySurface`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/displaySurface)
    6.  [`MediaTrackSettings.logicalSurface`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/logicalSurface)
    7.  [`MediaTrackSupportedConstraints.cursor`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints/cursor)
    8.  [`MediaTrackSupportedConstraints.displaySurface`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints/displaySurface)
    9.  [`MediaTrackSupportedConstraints.logicalSurface`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints/logicalSurface)
4.  Methods
    1.  [`MediaDevices.getDisplayMedia()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getDisplayMedia)

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
