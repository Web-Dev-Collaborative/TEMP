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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/MouseWheelEvent" class="breadcrumb-current-page"><span data-property="name">MouseWheelEvent</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Properties](#properties)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

MouseWheelEvent
===============

#### Non-standard

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

#### Deprecated

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The **`MouseWheelEvent`** interface represents events that occur due to the user turning a mouse wheel.

**Do not use this interface for wheel events.**

Like [`MouseScrollEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MouseScrollEvent), this interface is non-standard and deprecated. It was used in non-Gecko browsers only. Instead use the standard *[`WheelEvent`](https://developer.mozilla.org/en-US/docs/Web/API/WheelEvent).*

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

<table><tbody><tr class="odd"><td>Attribute</td><td>Type</td><td>Description</td></tr><tr class="even"><td><code>wheelDelta</code> <span class="badge inline readonly" title="This value may not be changed.">Read only </span></td><td><code>long</code></td><td>The distance in pixels (defined as so by MSDN, but the actual usage is different, see <code>mousewheel</code>).</td></tr><tr class="odd"><td><code>wheelDeltaX</code> <span class="badge inline readonly" title="This value may not be changed.">Read only </span></td><td><code>long</code>?</td><td>The value along horizontal axis of <code>wheelDelta</code>.</td></tr><tr class="even"><td><code>wheelDeltaY</code> <span class="badge inline readonly" title="This value may not be changed.">Read only </span></td><td><code>long</code>?</td><td>The value along vertical axis of <code>wheelDelta</code>.</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   An event type which is used by this event object: `mousewheel`
-   A standardized mouse wheel event object: [`WheelEvent`](https://developer.mozilla.org/en-US/docs/Web/API/WheelEvent)
-   Gecko's legacy mouse wheel event object: [`MouseScrollEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MouseScrollEvent)
-   The document in MSDN: <a href="https://msdn.microsoft.com/en-us/library/ie/ff974345(v=vs.85).aspx" class="external">MouseWheelEvent object</a>

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/mousewheelevent/index.html "Folder: en-us/web/api/mousewheelevent (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FMouseWheelEvent%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fmousewheelevent%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FMouseWheelEvent%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fmousewheelevent%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F5737ba49f3f0c3fc7587d329f1362a7a66afdd80%0A*+Document+last+modified%3A+2021-05-31T16%3A58%3A42.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22MouseWheelEvent%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/MouseWheelEvent/contributors.txt)

Change your languageSelect your preferred language English (US)中文 (简体)

Change language

#### Related Topics

1.  **[`MouseWheelEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MouseWheelEvent)**
2.  Related pages for DOM Events
    1.  [`CompositionEvent`](https://developer.mozilla.org/en-US/docs/Web/API/CompositionEvent)
    2.  [`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event)
    3.  [`EventListener`](https://developer.mozilla.org/en-US/docs/Web/API/EventListener)
    4.  [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)
    5.  [`FocusEvent`](https://developer.mozilla.org/en-US/docs/Web/API/FocusEvent)
    6.  [`InputEvent`](https://developer.mozilla.org/en-US/docs/Web/API/InputEvent)
    7.  [`KeyboardEvent`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent)
    8.  [`MouseEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent)
    9.  [`MouseScrollEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MouseScrollEvent)
    10. [`MutationEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MutationEvent)
    11. [`ProgressEvent`](https://developer.mozilla.org/en-US/docs/Web/API/ProgressEvent)
    12. [`UIEvent`](https://developer.mozilla.org/en-US/docs/Web/API/UIEvent)
    13. [`WheelEvent`](https://developer.mozilla.org/en-US/docs/Web/API/WheelEvent)

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
