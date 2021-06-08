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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/MouseScrollEvent" class="breadcrumb-current-page"><span data-property="name">MouseScrollEvent</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Method overview](#method_overview)
-   [Attributes](#attributes)
-   [Constants](#constants)
-   [Methods](#methods)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

MouseScrollEvent
================

#### Non-standard

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

#### Deprecated

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The **`MouseScrollEvent`** interface represents events that occur due to the user moving a mouse wheel or similar input device.

**Do not use this interface for wheel events.**

Like [`MouseWheelEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MouseWheelEvent), this interface is non-standard and deprecated. It was used in Gecko-based browsers only. Instead use the standard *[`WheelEvent`](https://developer.mozilla.org/en-US/docs/Web/API/WheelEvent).*

[Method overview](#method_overview "Permalink to Method overview")
------------------------------------------------------------------

<table><tbody><tr class="odd"><td><code>void initMouseScrollEvent(in DOMString typeArg, in boolean canBubbleArg, in boolean cancelableArg, in nsIDOMAbstractView viewArg, in long detailArg, in long screenXArg, in long screenYArg, in long clientXArg, in long clientYArg, in boolean ctrlKeyArg, in boolean altKeyArg, in boolean shiftKeyArg, in boolean metaKeyArg, in unsigned short buttonArg, in nsIDOMEventTarget relatedTargetArg, in long axis);</code></td></tr></tbody></table>

[Attributes](#attributes "Permalink to Attributes")
---------------------------------------------------

<table><tbody><tr class="odd"><td>Attribute</td><td>Type</td><td>Description</td></tr><tr class="even"><td><code>axis</code> <span class="badge inline readonly" title="This value may not be changed.">Read only </span></td><td><code>long</code></td><td>Indicates scroll direction.</td></tr></tbody></table>

[Constants](#constants "Permalink to Constants")
------------------------------------------------

### [Delta modes](#delta_modes "Permalink to Delta modes")

<table><tbody><tr class="odd"><td>Constant</td><td>Value</td><td>Description</td></tr><tr class="even"><td><code>HORIZONTAL_AXIS</code></td><td><code>0x01</code></td><td>The event is caused by horizontal wheel operation.</td></tr><tr class="odd"><td><code>VERTICAL_AXIS</code></td><td><code>0x02</code></td><td>The event is caused by vertical wheel operation.</td></tr></tbody></table>

[Methods](#methods "Permalink to Methods")
------------------------------------------

`initMouseScrollEvent()`  
See <a href="https://developer.mozilla.org/en-US/docs/XPCOM_Interface_Reference/nsIDOMMouseScrollEvent#initMouseScrollEvent%28%29" class="page-not-created" title="This is a link to an unwritten page">nsIDOMMouseScrollEvent::initMouseScrollEvent()</a>.

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   `DOMMouseScroll`
-   `MozMousePixelScroll`
-   Non-gecko browsers' legacy mouse wheel event object: [`MouseWheelEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MouseWheelEvent)
-   Standardized mouse wheel event object: [`WheelEvent`](https://developer.mozilla.org/en-US/docs/Web/API/WheelEvent)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/mousescrollevent/index.html "Folder: en-us/web/api/mousescrollevent (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FMouseScrollEvent%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fmousescrollevent%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FMouseScrollEvent%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fmousescrollevent%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F5737ba49f3f0c3fc7587d329f1362a7a66afdd80%0A*+Document+last+modified%3A+2021-05-31T16%3A58%3A42.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22MouseScrollEvent%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/MouseScrollEvent/contributors.txt)

Change your languageSelect your preferred language English (US)Polski中文 (简体)

Change language

#### Related Topics

1.  **[`MouseScrollEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MouseScrollEvent)**
2.  Inheritance:
    1.  [`MouseEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent)
    2.  [`UIEvent`](https://developer.mozilla.org/en-US/docs/Web/API/UIEvent)
    3.  [`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event)
3.  Related pages for DOM Events
    1.  [`CompositionEvent`](https://developer.mozilla.org/en-US/docs/Web/API/CompositionEvent)
    2.  [`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event)
    3.  [`EventListener`](https://developer.mozilla.org/en-US/docs/Web/API/EventListener)
    4.  [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)
    5.  [`FocusEvent`](https://developer.mozilla.org/en-US/docs/Web/API/FocusEvent)
    6.  [`InputEvent`](https://developer.mozilla.org/en-US/docs/Web/API/InputEvent)
    7.  [`KeyboardEvent`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent)
    8.  [`MouseEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent)
    9.  [`MouseWheelEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MouseWheelEvent)
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
