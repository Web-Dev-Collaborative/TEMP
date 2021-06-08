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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices" class="breadcrumb-penultimate"><span data-property="name">MediaDevices</span></a>
4.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getDisplayMedia" class="breadcrumb-current-page"><span data-property="name">MediaDevices.getDisplayMedia()</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Syntax](#syntax)
-   [Usage notes](#usage_notes)
-   [Example](#example)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

MediaDevices.getDisplayMedia()
==============================

<span class="seoSummary">The [`MediaDevices`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices) interface's `getDisplayMedia()` method prompts the user to select and grant permission to capture the contents of a display or portion thereof (such as a window) as a [`MediaStream`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream).</span> The resulting stream can then be recorded using the [MediaStream Recording API](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream_Recording_API) or transmitted as part of a [WebRTC](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API) session.

See [Using the Screen Capture API](https://developer.mozilla.org/en-US/docs/Web/API/Screen_Capture_API/Using_Screen_Capture) for more details and an example.

[Syntax](#syntax "Permalink to Syntax")
---------------------------------------

    var promise = navigator.mediaDevices.getDisplayMedia(constraints);

### [Parameters](#parameters "Permalink to Parameters")

`constraints` <span class="badge inline optional">Optional</span>  
An optional [`MediaStreamConstraints`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamConstraints) object specifying requirements for the returned [`MediaStream`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream). Since `getDisplayMedia()` requires a video track, the returned stream will have one even if no video track is expressly requested by the `constraints` object.

### [Return value](#return_value "Permalink to Return value")

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to a [`MediaStream`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream) containing a video track whose contents come from a user-selected screen area, as well as an optional audio track.

**Note:** Browser support for audio tracks varies, both in terms of whether or not they're supported at all by the media recorder and in terms of the which audio source or sourcoes are supported. Check the [compatibility table](#browser%0A____compatibility) for details for each browser.

### [Exceptions](#exceptions "Permalink to Exceptions")

Rejections of the returned promise are made by passing a [`DOMException`](https://developer.mozilla.org/en-US/docs/Web/API/DOMException) error object to the promise's failure handler. Possible errors are:

<span class="page-not-created">`AbortError`</span>  
An error or failure that doesn't match any of the other exceptions below occurred.

<span class="page-not-created">`InvalidStateError`</span>  
The call to `getDisplayMedia()` was not made from code running due to a user action, such as an event handler. Another potential cause for this event: the [`document`](https://developer.mozilla.org/en-US/docs/Web/API/Document) in whose context `getDisplayMedia()` was called is not fully active; for example, perhaps it is not the frontmost tab.

<span class="page-not-created">`NotAllowedError`</span>  
Permission to access a screen area was denied by the user, or the current browsing instance is not permitted access to screen sharing.

<span class="page-not-created">`NotFoundError`</span>  
No sources of screen video are available for capture.

<span class="page-not-created">`NotReadableError`</span>  
The user selected a screen, window, tab, or other source of screen data, but a hardware or operating system level error or lockout occurred, preventing the sharing of the selected source.

<span class="page-not-created">`OverconstrainedError`</span>  
After creating the stream, applying the specified `constraints` fails because no compatible stream could be generated.

[`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError)  
The specified `constraints` include constraints which are not permitted when calling `getDisplayMedia()`. These unsupported constraints are `advanced` and any constraints which in turn have a member named `min` or `exact`.

[Usage notes](#usage_notes "Permalink to Usage notes")
------------------------------------------------------

### [Privacy and security](#privacy_and_security "Permalink to Privacy and security")

Because `getDisplayMedia()` could be used in nefarious ways, it can be a source of significant privacy and security concerns. For that reason, the specification details measures browsers are required to take in order to fully support `getDisplayMedia()`.

-   The specified `constraints` can't be used to limit the options available to the user. Instead, they must be applied after the user chooses a source, in order to generate output that matches the constraints.
-   The go-ahead permission to use `getDisplayMedia()` cannot be persisted for reuse. The user must be prompted for permission every time.
-   The call to `getDisplayMedia()` must be made from code which is running in response to a user action, such as in an event handler.
-   Browsers are encouraged to provide a warning to users about sharing displays or windows that contain browsers, and to keep a close eye on what other content might be getting captured and shown to other users.

[Example](#example "Permalink to Example")
------------------------------------------

In the example below, a `startCapture()` method is created which initiates screen capture given a set of options specified by the `displayMediaOptions` parameter. The options are specified in the form of a [`MediaStreamConstraints`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamConstraints) object which specifies the preferred stream configuration and the [display surface](https://developer.mozilla.org/en-US/docs/Web/API/Screen_Capture_API/Using_Screen_Capture#visible_vs_logical_display_surfaces) from which video is to be captured.

    async function startCapture(displayMediaOptions) {
      let captureStream = null;

      try {
        captureStream = await navigator.mediaDevices.getDisplayMedia(displayMediaOptions);
      } catch(err) {
        console.error("Error: " + err);
      }
      return captureStream;
    }

This uses <span class="page-not-created">`await`</span> to asynchronously wait for `getDisplayMedia()` to resolve with a [`MediaStream`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream) which contains the display contents as requested by the specified options. The stream is then returned to the caller for use, perhaps for adding to a WebRTC call using [`RTCPeerConnection.addTrack()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/addTrack) to add the video track from the stream.

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-screen-share/#dom-mediadevices-getdisplaymedia" class="external">Screen Capture<br />
<span class="small">The definition of 'MediaDevices.getDisplayMedia()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Screen Capture API](https://developer.mozilla.org/en-US/docs/Web/API/Screen_Capture_API)
-   [Using the Screen Capture API](https://developer.mozilla.org/en-US/docs/Web/API/Screen_Capture_API/Using_Screen_Capture)
-   [Media Capture and Streams API](https://developer.mozilla.org/en-US/docs/Web/API/Media_Streams_API)
-   [WebRTC API](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API)
-   [`getUserMedia()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getUserMedia "getUserMedia()"): Capturing media from a camera and/or microphone

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/mediadevices/getdisplaymedia/index.html "Folder: en-us/web/api/mediadevices/getdisplaymedia (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FMediaDevices%2FgetDisplayMedia%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fmediadevices%2Fgetdisplaymedia%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FMediaDevices%2FgetDisplayMedia%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fmediadevices%2Fgetdisplaymedia%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F5737ba49f3f0c3fc7587d329f1362a7a66afdd80%0A*+Document+last+modified%3A+2021-05-31T16%3A58%3A42.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22MediaDevices.getDisplayMedia%28%29%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getDisplayMedia/contributors.txt)

Change your languageSelect your preferred language English (US)中文 (简体)

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
-   [Terms](https://www.mozilla.org/about/legal/terms/mozilla)
-   [Privacy](https://www.mozilla.org/privacy/websites/)
-   [Cookies](https://www.mozilla.org/privacy/websites/#cookies)
