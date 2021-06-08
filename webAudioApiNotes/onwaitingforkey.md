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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement" class="breadcrumb-penultimate"><span data-property="name">HTMLMediaElement</span></a>
4.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/onwaitingforkey" class="breadcrumb-current-page"><span data-property="name">HTMLMediaElement.onwaitingforkey</span></a>

Table of contents
-----------------

Table of contents

-   [Syntax](#syntax)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)

HTMLMediaElement.onwaitingforkey
================================

#### Experimental

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

<span class="seoSummary">The **`onwaitingforkey`** property of the [`HTMLMediaElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement) is an event handler, fired when a `waitingforkey` event  occurs, when playback is blocked while waiting for an encryption key.</span>

This interface inherits from the [`ExtendableEvent`](https://developer.mozilla.org/en-US/docs/Web/API/ExtendableEvent) interface.

[Syntax](#syntax "Permalink to Syntax")
---------------------------------------

    HTMLMediaElement.onwaitingforkey = function(waitingforkey) { ... }

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/encrypted-media/#dom-htmlmediaelement-onwaitingforkey" class="external">Encrypted Media Extensions<br />
<span class="small">The definition of 'onwaitingforkey' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/htmlmediaelement/onwaitingforkey/index.html "Folder: en-us/web/api/htmlmediaelement/onwaitingforkey (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FHTMLMediaElement%2Fonwaitingforkey%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fhtmlmediaelement%2Fonwaitingforkey%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FHTMLMediaElement%2Fonwaitingforkey%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fhtmlmediaelement%2Fonwaitingforkey%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fcb20a8045f6cbdbd224b1068e46c8644470dd8c3%0A*+Document+last+modified%3A+2021-06-01T09%3A10%3A31.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22HTMLMediaElement.onwaitingforkey%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Jun 1, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/onwaitingforkey/contributors.txt)

#### Related Topics

1.  **[Encrypted Media Extensions API](https://developer.mozilla.org/en-US/docs/Web/API/Encrypted_Media_Extensions_API)**
2.  **[`HTMLMediaElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement)**
3.  Properties
    1.  [`audioTracks`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/audioTracks)
    2.  [`autoplay`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/autoplay)
    3.  [`buffered`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/buffered)
    4.  [`controller`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/controller)
    5.  [`controls`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/controls)
    6.  [`controlsList`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/controlsList)
    7.  [`crossOrigin`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/crossOrigin)
    8.  [`currentSrc`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/currentSrc)
    9.  [`currentTime`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/currentTime)
    10. [`defaultMuted`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/defaultMuted)
    11. [`defaultPlaybackRate`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/defaultPlaybackRate)
    12. [`duration`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/duration)
    13. [`ended`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/ended)
    14. [`error`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/error)
    15. [`loop`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/loop)
    16. [`mediaGroup`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/mediaGroup)
    17. [`muted`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/muted)
    18. [`networkState`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/networkState)
    19. [`onerror`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/onerror)
    20. [`paused`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/paused)
    21. [`playbackRate`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/playbackRate)
    22. [`readyState`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/readyState)
    23. [`seekable`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/seekable)
    24. [`sinkId`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/sinkId)
    25. [`src`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/src)
    26. [`srcObject`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/srcObject)
    27. [`textTracks`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/textTracks)
    28. [`videoTracks`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/videoTracks)
    29. [`volume`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/volume)
4.  Methods
    1.  [`canPlayType()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/canPlayType)
    2.  [`captureStream()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/captureStream)
    3.  [`fastSeek()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/fastSeek)
    4.  [`load()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/load)
    5.  [`msInsertAudioEffect()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/msInsertAudioEffect)
    6.  [`pause()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/pause)
    7.  [`play()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/play)
    8.  [`seekToNextFrame()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/seekToNextFrame)
    9.  [`setMediaKeys()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/setMediaKeys)
    10. [`setSinkId()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/setSinkId)
5.  Events
    1.  [`abort`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/abort_event)
    2.  [`canplay`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/canplay_event)
    3.  [`canplaythrough`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/canplaythrough_event)
    4.  [`durationchange`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/durationchange_event)
    5.  [`emptied`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/emptied_event)
    6.  [`ended`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/ended_event)
    7.  [`error`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/error_event)
    8.  [`loadeddata`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/loadeddata_event)
    9.  [`loadedmetadata`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/loadedmetadata_event)
    10. [`loadstart`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/loadstart_event)
    11. [`pause`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/pause_event)
    12. [`play`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/play_event)
    13. [`progress`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/progress_event)
    14. [`ratechange`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/ratechange_event)
    15. [`seeked`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/seeked_event)
    16. [`seeking`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/seeking_event)
    17. [`stalled`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/stalled_event)
    18. [`suspend`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/suspend_event)
    19. [`timeupdate`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/timeupdate_event)
    20. [`volumechange`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/volumechange_event)
    21. [`waiting`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/waiting_event)
6.  Inheritance:
    1.  [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
    2.  [`Element`](https://developer.mozilla.org/en-US/docs/Web/API/Element)
    3.  [`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node)
    4.  [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)
7.  Related pages for Encrypted Media Extensions
    1.  [`HTMLMediaElement.mediaKeys`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/mediaKeys)
    2.  [`HTMLMediaElement.onencrypted`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/onencrypted)
    3.  [`HTMLMediaElement.setMediaKeys()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/setMediaKeys)
    4.  [`MediaKeySession`](https://developer.mozilla.org/en-US/docs/Web/API/MediaKeySession)
    5.  [`MediaKeySessionEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MediaKeySessionEvent)
    6.  [`MediaKeyStatusMap`](https://developer.mozilla.org/en-US/docs/Web/API/MediaKeyStatusMap)
    7.  [`MediaKeySystemAccess`](https://developer.mozilla.org/en-US/docs/Web/API/MediaKeySystemAccess)
    8.  [`MediaKeySystemConfiguration`](https://developer.mozilla.org/en-US/docs/Web/API/MediaKeySystemConfiguration)
    9.  [`MediaKeys`](https://developer.mozilla.org/en-US/docs/Web/API/MediaKeys)
    10. [`Navigator.requestMediaKeySystemAccess()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/requestMediaKeySystemAccess)

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
