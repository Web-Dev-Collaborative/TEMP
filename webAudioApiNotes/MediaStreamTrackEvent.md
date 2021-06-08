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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrackEvent" class="breadcrumb-current-page"><span data-property="name">MediaStreamTrackEvent</span></a>

Table of contents
-----------------

Table of contents

-   [Properties](#properties)
-   [Constructor](#constructor)
-   [Methods](#methods)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

MediaStreamTrackEvent
=====================

The **`MediaStreamTrackEvent`** interface represents events which indicate that a [`MediaStream`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream) has had tracks added to or removed from the stream through calls to [Media Stream API](https://developer.mozilla.org/en-US/docs/Web/API/Media_Streams_API) methods. These events are sent to the stream when these changes occur.

The events based on this interface are `addtrack` and `removetrack`

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

*Also inherits properties from its parent interface, [`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event).*

`track` <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
A [`MediaStreamTrack`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack) object representing the track which was added to the stream.

[Constructor](#constructor "Permalink to Constructor")
------------------------------------------------------

[`MediaStreamTrackEvent()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrackEvent/MediaStreamTrackEvent "MediaStreamTrackEvent()")  
Constructs a new `MediaStreamTrackEvent` with the specified configuration.

[Methods](#methods "Permalink to Methods")
------------------------------------------

*Also inherits methods from its parent [`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event).*

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#mediastreamtrackevent" class="external">Media Capture and Streams<br />
<span class="small">The definition of 'MediaStreamTrackEvent' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   `addtrack` and `removetrack` events
-   [`MediaStream`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream): [`onaddtrack`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream/onaddtrack "onaddtrack") and [`onremovetrack`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream/onremovetrack "onremovetrack")
-   [`MediaStreamTrack`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack)
-   [Media Streams API](https://developer.mozilla.org/en-US/docs/Web/API/Media_Streams_API)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/mediastreamtrackevent/index.html "Folder: en-us/web/api/mediastreamtrackevent (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FMediaStreamTrackEvent%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fmediastreamtrackevent%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FMediaStreamTrackEvent%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fmediastreamtrackevent%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F5737ba49f3f0c3fc7587d329f1362a7a66afdd80%0A*+Document+last+modified%3A+2021-05-31T16%3A58%3A42.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22MediaStreamTrackEvent%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrackEvent/contributors.txt)

#### Related Topics

1.  **[`MediaStreamTrackEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrackEvent)**
2.  Constructor
    1.  [`MediaStreamTrackEvent()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrackEvent/MediaStreamTrackEvent)
3.  Inheritance:
    1.  [`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event)

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
