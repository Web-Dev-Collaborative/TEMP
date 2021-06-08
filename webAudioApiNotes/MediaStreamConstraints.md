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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamConstraints" class="breadcrumb-current-page"><span data-property="name">MediaStreamConstraints</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Properties](#properties)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

MediaStreamConstraints
======================

The **`MediaStreamConstraints`** dictionary is used when calling [`getUserMedia()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getUserMedia "getUserMedia()") to specify what kinds of tracks should be included in the returned [`MediaStream`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream), and, optionally, to establish constraints for those tracks' settings.

To learn more about how constraints work, see [Capabilities, constraints, and settings](https://developer.mozilla.org/en-US/docs/Web/API/Media_Streams_API/Constraints).

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

Some combination—but not necessarily all—of the following properties will exist on the object.

### [Track constraints](#track_constraints "Permalink to Track constraints")

[`audio`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamConstraints/audio "audio")  
Either a Boolean (which indicates whether or not an audio track is requested) or a [`MediaTrackConstraints`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackConstraints) object providing the constraints which must be met by the audio track included in the returned [`MediaStream`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream). If constraints are specified, an audio track is inherently requested.

[`video`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamConstraints/video "video")  
Either a Boolean (which indicates whether or not a video track is requested) or a [`MediaTrackConstraints`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackConstraints) object providing the constraints which must be met by the video track included in the returned [`MediaStream`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream). If constraints are specified, a video track is inherently requested.

### [Security](#security "Permalink to Security")

<span class="page-not-created">`peerIdentity`</span>  
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) identifying the peer who has sole access to the stream. If this property is specified, only the indicated peer can receive and use the stream. Streams isolated in this way can only be displayed in a media element ([`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) or [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video)) where the content is protected just as if [CORS](https://developer.mozilla.org/en-US/docs/Glossary/CORS) cross-origin rules were in effect.

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [`MediaDevices.getUserMedia()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getUserMedia)
-   [`MediaStreamTrack.getConstraints()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/getConstraints)
-   [`MediaStreamTrack.applyConstraints()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/applyConstraints)
-   [`MediaDevices.getSupportedConstraints()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getSupportedConstraints)
-   [`MediaTrackSupportedConstraints`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints)
-   [`MediaStreamTrack.getSettings()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/getSettings)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/mediastreamconstraints/index.html "Folder: en-us/web/api/mediastreamconstraints (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FMediaStreamConstraints%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fmediastreamconstraints%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FMediaStreamConstraints%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fmediastreamconstraints%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Ff258e08dd3053632c642268ae5625a8295af5f23%0A*+Document+last+modified%3A+2021-06-03T19%3A09%3A29.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22MediaStreamConstraints%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Jun 3, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamConstraints/contributors.txt)

Change your languageSelect your preferred language English (US)日本語

Change language

#### Related Topics

1.  **[Media Streams API](https://developer.mozilla.org/en-US/docs/Web/API/Media_Streams_API)**
2.  **[`MediaStreamConstraints`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamConstraints)**
3.  Related pages for Media Capture and Streams
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
    18. [`MediaTrackSupportedConstraints`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints)
    19. [`Navigator.mediaDevices`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/mediaDevices)
    20. [`NavigatorUserMedia`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorUserMedia)
    21. [`NavigatorUserMediaError`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorUserMediaError)
    22. [`VideoStreamTrack`](https://developer.mozilla.org/en-US/docs/Web/API/VideoStreamTrack)
    23. [`navigator.mediaDevices.getUserMedia()`](https://developer.mozilla.org/en-US/docs/Web/API/navigator/mediaDevices.getUserMedia)

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
