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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStream" class="breadcrumb-penultimate"><span data-property="name">MediaStream</span></a>
4.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStream/onremovetrack" class="breadcrumb-current-page"><span data-property="name">MediaStream.onremovetrack</span></a>

Table of contents
-----------------

Table of contents

-   [Syntax](#syntax)
-   [Example](#example)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

MediaStream.onremovetrack
=========================

<span class="seoSummary">The **`MediaStream.onremovetrack`** property is an `event handler` which specifies a function to be called when the `removetrack` event occurs on a [`MediaStream`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream) instance. This happens when a track of any kind is removed from the media stream.</span> This event is fired when the browser removes a track from the stream (such as when a [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection) is renegotiated or a stream being captured using [`HTMLMediaElement.captureStream()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/captureStream) gets a new set of tracks because the media element being captured loaded a new source.

The `removetrack` event does *not* get fired when JavaScript code explicitly removes tracks from the stream (by calling <span class="page-not-created">`removeTrack()`</span>).

[Syntax](#syntax "Permalink to Syntax")
---------------------------------------

    MediaStream.onremovetrack = eventHandler;

### [Value](#value "Permalink to Value")

This should be set to a function which you provide that accepts as input a [`MediaStreamTrackEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrackEvent) object representing the `removetrack` event which has occurred. The [`MediaStreamTrack`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack) representing the track which was removed is specified in the event's <span class="page-not-created">`track`</span> property.

[Example](#example "Permalink to Example")
------------------------------------------

This example adds a listener which, when a track is removed from the stream, logs the track that was removed.

    stream.onremovetrack = function(event) {
      let trackList = document.getElementById("tracks");
      let label = document.createElement("li");

      label.textContent = `Removed: ${event.track.kind}: ${event.track.label}`;
      trackList.appendChild(label);
    };

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediastream-onremovetrack" class="external">Media Capture and Streams<br />
<span class="small">The definition of 'MediaStream.onremovetrack' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   The `removetrack` event and its type, [`MediaStreamTrackEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrackEvent).

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/mediastream/onremovetrack/index.html "Folder: en-us/web/api/mediastream/onremovetrack (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FMediaStream%2Fonremovetrack%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fmediastream%2Fonremovetrack%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FMediaStream%2Fonremovetrack%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fmediastream%2Fonremovetrack%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F5737ba49f3f0c3fc7587d329f1362a7a66afdd80%0A*+Document+last+modified%3A+2021-05-31T16%3A58%3A42.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22MediaStream.onremovetrack%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream/onremovetrack/contributors.txt)

#### Related Topics

1.  **[`MediaStream`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream)**
2.  Constructor
    1.  [`MediaStream()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream/MediaStream)
3.  Properties
    1.  [`active`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream/active)
    2.  [`ended`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream/ended)
    3.  [`id`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream/id)
    4.  [`onaddtrack`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream/onaddtrack)
    5.  *`onremovetrack`*
4.  Methods
    1.  [`addTrack()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream/addTrack)
    2.  [`clone()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream/clone)
    3.  [`getAudioTracks()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream/getAudioTracks)
    4.  [`getTrackById()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream/getTrackById)
    5.  [`getTracks()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream/getTracks)
    6.  [`getVideoTracks()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream/getVideoTracks)
5.  Events
    1.  [`addtrack`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream/addtrack_event)
    2.  [`removetrack`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream/removetrack_event)
6.  Inheritance:
    1.  [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)

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
