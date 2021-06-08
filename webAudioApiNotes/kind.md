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
3.  <a href="../MediaStreamTrack.html" class="breadcrumb-penultimate"><span data-property="name">MediaStreamTrack</span></a>
4.  <a href="kind.html" class="breadcrumb-current-page"><span data-property="name">MediaStreamTrack.kind</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Syntax](#syntax)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

MediaStreamTrack.kind
=====================

<span class="seoSummary">The `MediaStreamTrack.kind` read-only property returns a [`DOMString`](../DOMString.html) set to `"audio"` if the track is an audio track and to `"video"`, if it is a video track.</span> It doesn't change if the track is deassociated from its source.

[Syntax](#syntax "Permalink to Syntax")
---------------------------------------

    const type = track.kind

### [Value](#value "Permalink to Value")

The possible values are a [`DOMString`](../DOMString.html) with on of the following values:

-   `"audio"`: the track is an audio track.
-   `"video"`: the track is a video track.

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediastreamtrack-kind" class="external">Media Capture and Streams<br />
<span class="small">The definition of 'MediaStreamTrack.kind' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [WebRTC](../WebRTC_API.html)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/mediastreamtrack/kind/index.html "Folder: en-us/web/api/mediastreamtrack/kind (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FMediaStreamTrack%2Fkind%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fmediastreamtrack%2Fkind%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FMediaStreamTrack%2Fkind%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fmediastreamtrack%2Fkind%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F5737ba49f3f0c3fc7587d329f1362a7a66afdd80%0A*+Document+last+modified%3A+2021-05-31T16%3A58%3A42.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22MediaStreamTrack.kind%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](kind/contributors.txt)

Change your languageSelect your preferred language English (US)日本語한국어

Change language

#### Related Topics

1.  **[Media Streams API](../Media_Streams_API.html)**
2.  **[`MediaStreamTrack`](../MediaStreamTrack.html)**
3.  Properties
    1.  [`enabled`](enabled.html)
    2.  [`id`](id.html)
    3.  *`kind`*
    4.  [`label`](label.html)
    5.  [`muted`](muted.html)
    6.  [`onended`](onended.html)
    7.  [`onmute`](onmute.html)
    8.  [`onoverconstrained`](onoverconstrained.html)
    9.  [`onunmute`](onunmute.html)
    10. [`readyState`](readyState.html)
    11. [`remote`](remote.html)
4.  Methods
    1.  [`applyConstraints()`](applyConstraints.html)
    2.  [`clone()`](clone.html)
    3.  [`getCapabilities()`](getCapabilities.html)
    4.  [`getConstraints()`](getConstraints.html)
    5.  [`getSettings()`](getSettings.html)
    6.  [`stop()`](stop.html)
5.  Events
    1.  [`ended`](ended_event.html)
    2.  [`mute`](mute_event.html)
    3.  [`unmute`](unmute_event.html)
6.  Related pages for Media Capture and Streams
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
    13. [`MediaStreamTrackEvent`](../MediaStreamTrackEvent.html)
    14. [`MediaTrackCapabilities`](../MediaTrackCapabilities.html)
    15. [`MediaTrackConstraints`](../MediaTrackConstraints.html)
    16. [`MediaTrackSettings`](../MediaTrackSettings.html)
    17. [`MediaTrackSupportedConstraints`](../MediaTrackSupportedConstraints.html)
    18. [`Navigator.mediaDevices`](../Navigator/mediaDevices.html)
    19. [`NavigatorUserMedia`](../NavigatorUserMedia.html)
    20. [`NavigatorUserMediaError`](../NavigatorUserMediaError.html)
    21. [`VideoStreamTrack`](../VideoStreamTrack.html)
    22. [`navigator.mediaDevices.getUserMedia()`](../MediaDevices/getUserMedia.html)

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
