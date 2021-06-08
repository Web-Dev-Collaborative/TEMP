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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/ConstrainBoolean" class="breadcrumb-current-page"><span data-property="name">ConstrainBoolean</span></a>

Table of contents
-----------------

Table of contents

-   [Properties](#properties)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

ConstrainBoolean
================

The **`ConstrainBoolean`** dictionary is used to specify a constraint for a property whose value is a Boolean value. You can specify an exact value which must be matched, an ideal value that should be matched if at all possible, and a fallback value to attempt to match once all more specific constraints have been applied.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

`exact`  
A Boolean which indicates a value the property must have.

`ideal`  
A Boolean value indicating the ideal, but not required, value the property should ideally have. If possible, this value will be used, but the user agent will use the other value if it needs to in order to come up with a workable configuration.

You can also specify the value of the property as `true` or `false`, in which case the user agent will use that value if possible once all efforts have been made to match the `exact` and `ideal` values for other properties.

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-constrainboolean" class="external">Media Capture and Streams<br />
<span class="small">The definition of 'ConstrainBoolean' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

Technically, `ConstrainBoolean` is actually based on an intermediary dictionary named `ConstrainBooleanParameters`, which adds `exact` and `ideal` to the simple Boolean type. However, for the sake of documentation clarity, the intermediate type (present only because of quirks in [WebIDL](https://developer.mozilla.org/en-US/docs/Glossary/WebIDL) syntax) is ignored here.

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Media Capture and Streams API](https://developer.mozilla.org/en-US/docs/Web/API/Media_Streams_API)
-   [Capabilities, constraints, and settings](https://developer.mozilla.org/en-US/docs/Web/API/Media_Streams_API/Constraints)
-   [`MediaTrackConstraints`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackConstraints)
-   <span class="page-not-created">`MediaTrackCapabilities`</span>
-   [`MediaTrackSupportedConstraints`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/constrainboolean/index.html "Folder: en-us/web/api/constrainboolean (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FConstrainBoolean%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fconstrainboolean%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FConstrainBoolean%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fconstrainboolean%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fe085698aeab231f6d0c1d3bb7ea6288237946703%0A*+Document+last+modified%3A+2021-05-29T04%3A16%3A39.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22ConstrainBoolean%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 29, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/ConstrainBoolean/contributors.txt)

#### Related Topics

1.  **[Media Streams API](https://developer.mozilla.org/en-US/docs/Web/API/Media_Streams_API)**
2.  **[`ConstrainBoolean`](https://developer.mozilla.org/en-US/docs/Web/API/ConstrainBoolean)**
3.  Related pages for Media Capture and Streams
    1.  [`AudioStreamTrack`](https://developer.mozilla.org/en-US/docs/Web/API/AudioStreamTrack)
    2.  [`BlobEvent`](https://developer.mozilla.org/en-US/docs/Web/API/BlobEvent)
    3.  [`CanvasCaptureMediaStream`](https://developer.mozilla.org/en-US/docs/Web/API/CanvasCaptureMediaStream)
    4.  [`ConstrainDOMString`](https://developer.mozilla.org/en-US/docs/Web/API/ConstrainDOMString)
    5.  [`ConstrainDouble`](https://developer.mozilla.org/en-US/docs/Web/API/ConstrainDouble)
    6.  [`ConstrainLong`](https://developer.mozilla.org/en-US/docs/Web/API/ConstrainLong)
    7.  [`DoubleRange`](https://developer.mozilla.org/en-US/docs/Web/API/DoubleRange)
    8.  [`HTMLCanvasElement.captureStream()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/captureStream)
    9.  [`LongRange`](https://developer.mozilla.org/en-US/docs/Web/API/LongRange)
    10. [`MediaDevices`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices)
    11. [`MediaStream`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream)
    12. [`MediaStreamTrack`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack)
    13. [`MediaStreamTrackEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrackEvent)
    14. [`MediaTrackCapabilities`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackCapabilities)
    15. [`MediaTrackConstraints`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackConstraints)
    16. [`MediaTrackSettings`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings)
    17. [`MediaTrackSupportedConstraints`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints)
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
