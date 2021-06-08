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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/WheelEvent" class="breadcrumb-current-page"><span data-property="name">WheelEvent</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Constructor](#constructor)
-   [Properties](#properties)
-   [Methods](#methods)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

WheelEvent
==========

The **`WheelEvent`** interface represents events that occur due to the user moving a mouse wheel or similar input device.

**Important: This is the standard wheel event interface to use.** Old versions of browsers implemented the non-standard and non-cross-browser-compatible [`MouseWheelEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MouseWheelEvent) and [`MouseScrollEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MouseScrollEvent) interfaces. Use this interface and avoid the non-standard ones.

**Do not confuse the [`wheel`](https://developer.mozilla.org/en-US/docs/Web/API/Element/wheel_event "wheel") event with the [`scroll`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scroll_event "scroll") event:** The default action of a `wheel` event is implementation-defined. Thus, a `wheel` event doesn't necessarily dispatch a `scroll` event. Even when it does, that doesn't mean that the `delta*` values in the `wheel` event necessarily reflect the content's scrolling direction. Therefore, do not rely on `delta*` properties to get the content's scrolling direction. Instead, detect value changes to [`scrollLeft`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollLeft "scrollLeft") and [`scrollTop`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollTop "scrollTop") of the target in the `scroll` event.

[Constructor](#constructor "Permalink to Constructor")
------------------------------------------------------

[`WheelEvent()`](https://developer.mozilla.org/en-US/docs/Web/API/WheelEvent/WheelEvent "WheelEvent()")  
Creates a `WheelEvent` object.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

*This interface inherits properties from its ancestors, [`MouseEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent), [`UIEvent`](https://developer.mozilla.org/en-US/docs/Web/API/UIEvent), and [`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event).*

[`WheelEvent.deltaX`](https://developer.mozilla.org/en-US/docs/Web/API/WheelEvent/deltaX)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a `double` representing the horizontal scroll amount.

[`WheelEvent.deltaY`](https://developer.mozilla.org/en-US/docs/Web/API/WheelEvent/deltaY)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a `double` representing the vertical scroll amount.

[`WheelEvent.deltaZ`](https://developer.mozilla.org/en-US/docs/Web/API/WheelEvent/deltaZ)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a `double` representing the scroll amount for the z-axis.

[`WheelEvent.deltaMode`](https://developer.mozilla.org/en-US/docs/Web/API/WheelEvent/deltaMode)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns an `unsigned long` representing the unit of the `delta*` values' scroll amount. Permitted values are:

<table><thead><tr class="header"><th>Constant</th><th>Value</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>WheelEvent.DOM_DELTA_PIXEL</code></td><td><code>0x00</code></td><td>The <code>delta*</code> values are specified in pixels.</td></tr><tr class="even"><td><code>WheelEvent.DOM_DELTA_LINE</code></td><td><code>0x01</code></td><td>The <code>delta*</code> values are specified in lines.</td></tr><tr class="odd"><td><code>WheelEvent.DOM_DELTA_PAGE</code></td><td><code>0x02</code></td><td>The <code>delta*</code> values are specified in pages.</td></tr></tbody></table>

[Methods](#methods "Permalink to Methods")
------------------------------------------

*This interface doesn't define any specific methods, but inherits methods from its ancestors, [`MouseEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent), [`UIEvent`](https://developer.mozilla.org/en-US/docs/Web/API/UIEvent), and [`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event).*

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/uievents/#interface-wheelevent" class="external">UI Events<br />
<span class="small">The definition of 'The <code>WheelEvent</code> interface' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#interface-wheelevent" class="external">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'WheelEvent' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [`wheel`](https://developer.mozilla.org/en-US/docs/Web/API/Element/wheel_event "wheel") event
-   Interfaces replaced by this one:
    -   Gecko's legacy mouse wheel event object: [`MouseScrollEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MouseScrollEvent)
    -   Non-gecko browsers' legacy mouse wheel event object: [`MouseWheelEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MouseWheelEvent)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/wheelevent/index.html "Folder: en-us/web/api/wheelevent (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWheelEvent%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fwheelevent%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWheelEvent%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fwheelevent%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F94c536f9b3a50303a85e7963a4ff4958d1aec382%0A*+Document+last+modified%3A+2021-05-31T17%3A13%3A02.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22WheelEvent%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/WheelEvent/contributors.txt)

Change your languageSelect your preferred language English (US)EspañolFrançais日本語中文 (简体)正體中文 (繁體)

Change language

#### Related Topics

1.  **[`WheelEvent`](https://developer.mozilla.org/en-US/docs/Web/API/WheelEvent)**
2.  Constructor
    1.  [`WheelEvent()`](https://developer.mozilla.org/en-US/docs/Web/API/WheelEvent/WheelEvent)
3.  Properties
    1.  [`deltaMode`](https://developer.mozilla.org/en-US/docs/Web/API/WheelEvent/deltaMode)
    2.  [`deltaX`](https://developer.mozilla.org/en-US/docs/Web/API/WheelEvent/deltaX)
    3.  [`deltaY`](https://developer.mozilla.org/en-US/docs/Web/API/WheelEvent/deltaY)
    4.  [`deltaZ`](https://developer.mozilla.org/en-US/docs/Web/API/WheelEvent/deltaZ)
4.  Inheritance:
    1.  [`MouseEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent)
    2.  [`UIEvent`](https://developer.mozilla.org/en-US/docs/Web/API/UIEvent)
    3.  [`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event)
5.  Related pages for DOM Events
    1.  [`CompositionEvent`](https://developer.mozilla.org/en-US/docs/Web/API/CompositionEvent)
    2.  [`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event)
    3.  [`EventListener`](https://developer.mozilla.org/en-US/docs/Web/API/EventListener)
    4.  [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)
    5.  [`FocusEvent`](https://developer.mozilla.org/en-US/docs/Web/API/FocusEvent)
    6.  [`InputEvent`](https://developer.mozilla.org/en-US/docs/Web/API/InputEvent)
    7.  [`KeyboardEvent`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent)
    8.  [`MouseEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent)
    9.  [`MouseScrollEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MouseScrollEvent)
    10. [`MouseWheelEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MouseWheelEvent)
    11. [`MutationEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MutationEvent)
    12. [`ProgressEvent`](https://developer.mozilla.org/en-US/docs/Web/API/ProgressEvent)
    13. [`UIEvent`](https://developer.mozilla.org/en-US/docs/Web/API/UIEvent)

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
