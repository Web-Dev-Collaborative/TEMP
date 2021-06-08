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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack" class="breadcrumb-penultimate"><span data-property="name">MediaStreamTrack</span></a>
4.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/applyConstraints" class="breadcrumb-current-page"><span data-property="name">MediaStreamTrack.applyConstraints()</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Syntax](#syntax)
-   [Examples](#examples)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

MediaStreamTrack.applyConstraints()
===================================

<span class="seoSummary">The `applyConstraints`**`()`** method of the [`MediaStreamTrack`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack) interface applies a set of constraints to the track; these constraints let the Web site or app establish ideal values and acceptable ranges of values for the constrainable properties of the track, such as frame rate, dimensions, echo cancelation, and so forth.</span>

Constraints can be used to ensure that the media meets certain guidelines you prefer. For example, you may prefer high-density video but require that the frame rate be a little low to help keep the data rate low enough not overtax the network. Constraints can also specify ideal and/or acceptable sizes or ranges of sizes. See [Applying constraints](https://developer.mozilla.org/en-US/docs/Web/API/Media_Streams_API/Constraints#applying_constraints) in [Capabilities, constraints, and settings](https://developer.mozilla.org/en-US/docs/Web/API/Media_Streams_API/Constraints) for more information on how to apply your preferred constraints.

[Syntax](#syntax "Permalink to Syntax")
---------------------------------------

    const appliedPromise = track.applyConstraints([constraints])

### [Parameters](#parameters "Permalink to Parameters")

`constraints` <span class="badge inline optional">Optional</span>  
A [`MediaTrackConstraints`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackConstraints) object listing the constraints to apply to the track's constrainable properties; any existing constraints are replaced with the new values specified, and any constrainable properties not included are restored to their default constraints. If this parameter is omitted, all currently set custom constraints are cleared. This object represents the basic set of constraints that must apply for the [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) to resolve. The object may contain an advanced property containing an array of additional `MediaTrackConstraints` objects, which are treated as exact requires. 

### [Return value](#return_value "Permalink to Return value")

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which resolves when the constraints have been successfully applied. If the constraints cannot be applied, the promise is rejected with a <span class="page-not-created">`MediaStreamError`</span> whose name is `OverconstrainedError`, to indicate that the constraints could not be met. This can happen if the specified constraints are too strict to find a match when attempting to configure the track.

[Examples](#examples "Permalink to Examples")
---------------------------------------------

The following shows how to specify a basic and advanced set of constraints. It specifies that the page or web app needs a width between 640 and 1280 and a height between 480 and 720, with the later number in each pair being preferred. The advanced property further specifies that an image size of 1920 by 1280 is the preferred or an aspect ratio of 1.333 if that is not available. Note that these constraints also illustrate what the spec refers to as a *backoff strategy*.

    const constraints = {
      width: {min: 640, ideal: 1280},
      height: {min: 480, ideal: 720},
      advanced: [
        {width: 1920, height: 1280},
        {aspectRatio: 1.333}
      ]
    };

    navigator.mediaDevices.getUserMedia({ video: true })
    .then(mediaStream => {
      const track = mediaStream.getVideoTracks()[0];
      track.applyConstraints(constraints)
      .then(() => {
        // Do something with the track such as using the Image Capture API.
      })
      .catch(e => {
        // The constraints could not be satisfied by the available devices.
      });
    });

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediatrackconstraints" class="external">Media Capture and Streams<br />
<span class="small">The definition of 'applyConstraints()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://w3c.github.io/mediacapture-image/#mediatrackconstraintset-section" class="external">MediaStream Image Capture<br />
<span class="small">The definition of 'applyConstraints()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds image constraints.</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [MediaStream Image Capture API](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream_Image_Capture_API)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/mediastreamtrack/applyconstraints/index.html "Folder: en-us/web/api/mediastreamtrack/applyconstraints (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FMediaStreamTrack%2FapplyConstraints%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fmediastreamtrack%2Fapplyconstraints%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FMediaStreamTrack%2FapplyConstraints%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fmediastreamtrack%2Fapplyconstraints%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F5737ba49f3f0c3fc7587d329f1362a7a66afdd80%0A*+Document+last+modified%3A+2021-05-31T16%3A58%3A42.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22MediaStreamTrack.applyConstraints%28%29%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/applyConstraints/contributors.txt)

Change your languageSelect your preferred language English (US)한국어

Change language

#### Related Topics

1.  **[Media Streams API](https://developer.mozilla.org/en-US/docs/Web/API/Media_Streams_API)**
2.  **[`MediaStreamTrack`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack)**
3.  Properties
    1.  [`enabled`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/enabled)
    2.  [`id`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/id)
    3.  [`kind`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/kind)
    4.  [`label`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/label)
    5.  [`muted`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/muted)
    6.  [`onended`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/onended)
    7.  [`onmute`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/onmute)
    8.  [`onoverconstrained`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/onoverconstrained)
    9.  [`onunmute`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/onunmute)
    10. [`readyState`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/readyState)
    11. [`remote`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/remote)
4.  Methods
    1.  *`applyConstraints()`*
    2.  [`clone()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/clone)
    3.  [`getCapabilities()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/getCapabilities)
    4.  [`getConstraints()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/getConstraints)
    5.  [`getSettings()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/getSettings)
    6.  [`stop()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/stop)
5.  Events
    1.  [`ended`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/ended_event)
    2.  [`mute`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/mute_event)
    3.  [`unmute`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/unmute_event)
6.  Related pages for Media Capture and Streams
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
-   [Terms](https://www.mozilla.org/about/legal/terms/mozilla)
-   [Privacy](https://www.mozilla.org/privacy/websites/)
-   [Cookies](https://www.mozilla.org/privacy/websites/#cookies)
