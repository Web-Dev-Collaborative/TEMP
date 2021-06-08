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
4.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/unmute_event" class="breadcrumb-current-page"><span data-property="name">MediaStreamTrack: unmute event</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Examples](#examples)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

MediaStreamTrack: unmute event
==============================

<span class="seoSummary">The `unmute` event is sent to a [`MediaStreamTrack`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack) when the track's source is once again able to provide media data after a period of not being able to do so.</span> This ends the [`muted`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/muted "muted") state that began with the [`mute`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/mute_event "mute") event.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/Event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/onunmute" title="onunmute"><code>onunmute</code></a></td></tr></tbody></table>

**Note:** The condition that most people think of as "muted" (that is, a user-controllable way to silence a track) is actually managed using the [`MediaStreamTrack.enabled`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/enabled) property, for which there are no events.

[Examples](#examples "Permalink to Examples")
---------------------------------------------

In this example, event handlers are established for the [`mute`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/mute_event "mute") and `unmute` events in order to detect when the media is not flowing from the source for the [`MediaStreamTrack`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack) stored in the variable `musicTrack`.

    musicTrack.addEventListener("mute", event => {
      document.getElementById("timeline-widget").style.backgroundColor = "#aaa";
    }, false);

    musicTrack.addEventListener("unmute", event => {
     document.getElementById("timeline-widget").style.backgroundColor = "#fff";
    }, false);

With these event handlers in place, when the track `musicTrack` enters its [`muted`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/muted "muted") state, the element with the ID `timeline-widget` gets its background color changed to `#aaa`. When the track exits the muted state—detected by the arrival of an `unmuted` event—the background color is restored to white.

You can also use the [`onunmute`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/onunmute "onunmute") event handler property to set up a handler for this event; similarly, the [`onmute`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/onmute "onmute") event handler is available for setting up a handler for the `mute` event. The following example shows this:

    musicTrack.onmute = event => {
      document.getElementById("timeline-widget").style.backgroundColor = "#aaa";
    }

    musicTrack.mute = event = > {
      document.getElementById("timeline-widget").style.backgroundColor = "#fff";
    }

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#event-mediastreamtrack-unmute" class="external">Media Capture and Streams<br />
<span class="small">The definition of 'unmute' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [`onunmute`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/onunmute "onunmute") event handler property
-   [`mute`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/mute_event "mute") event

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/mediastreamtrack/unmute_event/index.html "Folder: en-us/web/api/mediastreamtrack/unmute_event (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FMediaStreamTrack%2Funmute_event%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fmediastreamtrack%2Funmute_event%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FMediaStreamTrack%2Funmute_event%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fmediastreamtrack%2Funmute_event%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F5737ba49f3f0c3fc7587d329f1362a7a66afdd80%0A*+Document+last+modified%3A+2021-05-31T16%3A58%3A42.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22MediaStreamTrack%3A+unmute+event%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/unmute_event/contributors.txt)

Change your languageSelect your preferred language English (US)日本語

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
    1.  [`applyConstraints()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/applyConstraints)
    2.  [`clone()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/clone)
    3.  [`getCapabilities()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/getCapabilities)
    4.  [`getConstraints()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/getConstraints)
    5.  [`getSettings()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/getSettings)
    6.  [`stop()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/stop)
5.  Events
    1.  [`ended`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/ended_event)
    2.  [`mute`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/mute_event)
    3.  *`unmute`*
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
