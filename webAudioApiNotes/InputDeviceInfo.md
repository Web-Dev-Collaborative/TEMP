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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/InputDeviceInfo" class="breadcrumb-current-page"><span data-property="name">InputDeviceInfo</span></a>

Table of contents
-----------------

Table of contents

-   [Methods](#methods)
-   [Examples](#examples)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)

InputDeviceInfo
===============

The **`InputDeviceInfo`** interface of the [Media Streams API](https://developer.mozilla.org/en-US/docs/Web/API/Media_Streams_API) gives access to the capabilities of the input device that it represents.

`InputDeviceInfo` objects are returned by [`MediaDevices.enumerateDevices()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/enumerateDevices) if the returned device is an audio or video input device.

[Methods](#methods "Permalink to Methods")
------------------------------------------

[`InputDeviceInfo.getCapabilities()`](https://developer.mozilla.org/en-US/docs/Web/API/InputDeviceInfo/getCapabilities)  
Returns a `MediaTrackCapabilities` object describing the primary audio or video track of a device's `MediaStream`.

[Examples](#examples "Permalink to Examples")
---------------------------------------------

The following example gets all media devices with [`MediaDevices.enumerateDevices()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/enumerateDevices). If any of the devices are input devices then `console.log(device)` will print an `InputDeviceInfo` object to the console.

    navigator.mediaDevices.enumerateDevices()
      .then(function(devices) {
        devices.forEach(function(device) {
          console.log(device); // an InputDeviceInfo object if the device is an input device, otherwise a MediaDeviceInfo object.
        });
      })

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-inputdeviceinfo" class="external">Media Capture and Streams<br />
<span class="small">The definition of 'InputDeviceInfo' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/inputdeviceinfo/index.html "Folder: en-us/web/api/inputdeviceinfo (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FInputDeviceInfo%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Finputdeviceinfo%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FInputDeviceInfo%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Finputdeviceinfo%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fafb900789aa9c9f3fb0192a9ea1ae6e5ffb0d231%0A*+Document+last+modified%3A+2021-05-31T00%3A59%3A40.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22InputDeviceInfo%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/InputDeviceInfo/contributors.txt)

#### Related Topics

1.  **[Media Streams API](https://developer.mozilla.org/en-US/docs/Web/API/Media_Streams_API)**
2.  Guides
    1.  [Capabilities, constraints, and settings](https://developer.mozilla.org/en-US/docs/Web/API/Media_Streams_API/Constraints)
3.  Interfaces
    1.  [`AudioStreamTrack`](https://developer.mozilla.org/en-US/docs/Web/API/AudioStreamTrack)
    2.  [`BlobEvent`](https://developer.mozilla.org/en-US/docs/Web/API/BlobEvent)
    3.  [`CanvasCaptureMediaStream`](https://developer.mozilla.org/en-US/docs/Web/API/CanvasCaptureMediaStream)
    4.  [`MediaDevices`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices)
    5.  [`MediaStream`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream)
    6.  [`MediaStreamTrack`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack)
    7.  [`MediaStreamTrackEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrackEvent)
    8.  [`MediaTrackCapabilities`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackCapabilities)
    9.  [`MediaTrackConstraints`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackConstraints)
    10. [`MediaTrackSettings`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings)
    11. [`MediaTrackSupportedConstraints`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints)
    12. [`NavigatorUserMedia`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorUserMedia)
    13. [`NavigatorUserMediaError`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorUserMediaError)
    14. [`VideoStreamTrack`](https://developer.mozilla.org/en-US/docs/Web/API/VideoStreamTrack)
    15. [`DoubleRange`](https://developer.mozilla.org/en-US/docs/Web/API/DoubleRange)
    16. [`ConstrainDouble`](https://developer.mozilla.org/en-US/docs/Web/API/ConstrainDouble)
    17. [`LongRange`](https://developer.mozilla.org/en-US/docs/Web/API/LongRange)
    18. [`ConstrainLong`](https://developer.mozilla.org/en-US/docs/Web/API/ConstrainLong)
    19. [`ConstrainBoolean`](https://developer.mozilla.org/en-US/docs/Web/API/ConstrainBoolean)
    20. [`ConstrainDOMString`](https://developer.mozilla.org/en-US/docs/Web/API/ConstrainDOMString)
4.  Properties
    1.  [`Navigator.mediaDevices`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/mediaDevices)
5.  Methods
    1.  [`HTMLCanvasElement.captureStream()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/captureStream)
    2.  [`navigator.mediaDevices.getUserMedia()`](https://developer.mozilla.org/en-US/docs/Web/API/navigator/mediaDevices.getUserMedia)
6.  Events
    1.  [`HTMLMediaElement`: `ended`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/ended_event)
    2.  [`HTMLMediaElement`: `ratechange`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/ratechange_event)

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
