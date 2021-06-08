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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/TextTrack" class="breadcrumb-current-page"><span data-property="name">TextTrack</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Properties](#properties)
-   [Events](#events)
-   [Methods](#methods)
-   [Example](#example)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

TextTrack
=========

The `TextTrack` interface—part of the API for handling WebVTT (text tracks on media presentations)—describes and controls the text track associated with a particular [`<track>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/track) element.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

*This interface also inherits properties from [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget).*

<span class="page-not-created">`TextTrack.activeCues`</span> <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
A [`TextTrackCueList`](https://developer.mozilla.org/en-US/docs/Web/API/TextTrackCueList) object listing the currently active set of text track cues. Track cues are active if the current playback position of the media is between the cues' start and end times. Thus, for displayed cues such as captions or subtitles, the active cues are currently being displayed.

<span class="page-not-created">`TextTrack.cues`</span> <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
A [`TextTrackCueList`](https://developer.mozilla.org/en-US/docs/Web/API/TextTrackCueList) which contains all of the track's cues.

<span class="page-not-created">`TextTrack.id`</span> <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) which identifies the track, if it has one. If it doesn't have an ID, then this value is an empty string (`""`). If the `TextTrack` is associated with a [`<track>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/track) element, then the track's ID matches the element's ID.

<span class="page-not-created">`TextTrack.inBandMetadataTrackDispatchType`</span> <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) which indicates the track's in-band metadata track dispatch type. ***needs details***

<span class="page-not-created">`TextTrack.kind`</span> <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) indicating what kind of text track the `TextTrack` describes. The value must be one of those in the TextTrackKind enum.

<span class="page-not-created">`TextTrack.label`</span> <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
A human-readable [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) which contains the text track's label, if one is present; otherwise, this is an empty string (`""`), in which case a custom label may need to be generated by your code using other attributes of the track, if the track's label needs to be exposed to the user.

<span class="page-not-created">`TextTrack.language`</span> <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) which specifies the text language in which the text track's contents is written. The value must adhere to the format specified in the <a href="https://datatracker.ietf.org/doc/html/bcp47" class="external">Tags for Identifying Languages</a> (<a href="https://datatracker.ietf.org/doc/html/bcp47" class="external">BCP 47</a>) document from the IETF, just like the HTML [`lang`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#attr-lang) attribute. For example, this can be `"en-US"` for United States English or `"pt-BR"` for Brazilian Portuguese.

[`TextTrack.mode`](https://developer.mozilla.org/en-US/docs/Web/API/TextTrack/mode)  
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) specifying the track's current mode. Changing this property's value changes the track's current mode to match. Permitted values are listed under [Text track mode constants](https://developer.mozilla.org/en-US/docs/Web/API/TextTrack/mode#text_track_mode_constants). The default is `disabled`, unless the [`<track>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/track) element's [`default`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/track#attr-default) Boolean attribute is specified, in which case the default mode is `started`.

[Events](#events "Permalink to Events")
---------------------------------------

`cuechange`  
Fired when cues are entered and exited. A given text cue appears when the cue is entered and disappears when the cue is exited.  
Also available via the `oncuechange` property.

[Methods](#methods "Permalink to Methods")
------------------------------------------

*This interface also inherits methods from [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget).*

<span class="page-not-created">`TextTrack.addCue()`</span>  
Adds a cue (specified as a [`TextTrackCue`](https://developer.mozilla.org/en-US/docs/Web/API/TextTrackCue) object to the track's list of cues.

<span class="page-not-created">`TextTrack.removeCue()`</span>  
Removes a cue (specified as a [`TextTrackCue`](https://developer.mozilla.org/en-US/docs/Web/API/TextTrackCue) object from the track's list of cues.

[Example](#example "Permalink to Example")
------------------------------------------

tbd

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#texttrack" class="external">HTML Living Standard<br />
<span class="small">The definition of 'TextTrack' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [WebVTT](https://developer.mozilla.org/en-US/docs/Web/API/WebVTT_API)
-   [`TextTrackCueList`](https://developer.mozilla.org/en-US/docs/Web/API/TextTrackCueList)
-   [`VTTCue`](https://developer.mozilla.org/en-US/docs/Web/API/VTTCue)
-   [`<track>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/track)
-   [`HTMLTrackElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTrackElement)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/texttrack/index.html "Folder: en-us/web/api/texttrack (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FTextTrack%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Ftexttrack%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FTextTrack%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Ftexttrack%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F5433cb8d4a62d2dac01548bb2f4ef643e16a0a2b%0A*+Document+last+modified%3A+2021-05-31T16%3A26%3A56.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22TextTrack%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/TextTrack/contributors.txt)

Change your languageSelect your preferred language English (US)Español日本語

Change language

#### Related Topics

1.  **[WebVTT API](https://developer.mozilla.org/en-US/docs/Web/API/WebVTT_API)**
2.  **[`TextTrack`](https://developer.mozilla.org/en-US/docs/Web/API/TextTrack)**
3.  Properties
    1.  [`mode`](https://developer.mozilla.org/en-US/docs/Web/API/TextTrack/mode)
4.  Events
    1.  [`cuechange`](https://developer.mozilla.org/en-US/docs/Web/API/TextTrack/cuechange_event)
5.  Inheritance:
    1.  [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)
6.  Related pages for WebVTT
    1.  [`TextTrackCue`](https://developer.mozilla.org/en-US/docs/Web/API/TextTrackCue)
    2.  [`TextTrackCueList`](https://developer.mozilla.org/en-US/docs/Web/API/TextTrackCueList)
    3.  [`TextTrackList`](https://developer.mozilla.org/en-US/docs/Web/API/TextTrackList)
    4.  [`TrackEvent`](https://developer.mozilla.org/en-US/docs/Web/API/TrackEvent)
    5.  [`VTTCue`](https://developer.mozilla.org/en-US/docs/Web/API/VTTCue)
    6.  [`VTTRegion`](https://developer.mozilla.org/en-US/docs/Web/API/VTTRegion)

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
