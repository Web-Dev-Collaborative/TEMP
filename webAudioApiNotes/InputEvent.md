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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/InputEvent" class="breadcrumb-current-page"><span data-property="name">InputEvent</span></a>

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

InputEvent
==========

The **`InputEvent`** interface represents an event notifying the user of editable content changes.

[Constructor](#constructor "Permalink to Constructor")
------------------------------------------------------

[`InputEvent()`](https://developer.mozilla.org/en-US/docs/Web/API/InputEvent/InputEvent "InputEvent()")  
Creates an `InputEvent` object.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

*This interface inherits properties from its parents, [`UIEvent`](https://developer.mozilla.org/en-US/docs/Web/API/UIEvent) and [`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event).*

[`InputEvent.data`](https://developer.mozilla.org/en-US/docs/Web/API/InputEvent/data)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) with the inserted characters. This may be an empty string if the change doesn't insert text (such as when deleting characters, for example).

[`InputEvent.dataTransfer`](https://developer.mozilla.org/en-US/docs/Web/API/InputEvent/dataTransfer)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`DataTransfer`](https://developer.mozilla.org/en-US/docs/Web/API/DataTransfer) object containing information about richtext or plaintext data being added to or removed from editable content.

[`InputEvent.inputType`](https://developer.mozilla.org/en-US/docs/Web/API/InputEvent/inputType)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the type of change for editable content such as, for example, inserting, deleting, or formatting text. See the property page for a complete list of input types.

[`InputEvent.isComposing`](https://developer.mozilla.org/en-US/docs/Web/API/InputEvent/isComposing)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) value indicating if the event is fired after `compositionstart` and before `compositionend`.

[Methods](#methods "Permalink to Methods")
------------------------------------------

*This interface inherits methods from its parents, [`UIEvent`](https://developer.mozilla.org/en-US/docs/Web/API/UIEvent) and [`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event).*

[`InputEvent.getTargetRanges()`](https://developer.mozilla.org/en-US/docs/Web/API/InputEvent/getTargetRanges)  
Returns an array of static ranges that will be affected by a change to the DOM if the input event is not canceled.

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/input-events/#interface-InputEvent" class="external">Input Events Level 2<br />
<span class="small">The definition of 'InputEvent' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr><tr class="even"><td><a href="https://w3c.github.io/uievents/#interface-inputevent" class="external">UI Events<br />
<span class="small">The definition of 'InputEvent' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [`beforeinput` event](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/beforeinput_event)
-   [`input` event](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/input_event)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/inputevent/index.html "Folder: en-us/web/api/inputevent (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FInputEvent%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Finputevent%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FInputEvent%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Finputevent%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fafb900789aa9c9f3fb0192a9ea1ae6e5ffb0d231%0A*+Document+last+modified%3A+2021-05-31T00%3A59%3A40.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22InputEvent%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/InputEvent/contributors.txt)

Change your languageSelect your preferred language English (US)Français日本語Русский中文 (简体)

Change language

#### Related Topics

1.  **[`InputEvent`](https://developer.mozilla.org/en-US/docs/Web/API/InputEvent)**
2.  Constructor
    1.  [`InputEvent()`](https://developer.mozilla.org/en-US/docs/Web/API/InputEvent/InputEvent)
3.  Properties
    1.  [`data`](https://developer.mozilla.org/en-US/docs/Web/API/InputEvent/data)
    2.  [`dataTransfer`](https://developer.mozilla.org/en-US/docs/Web/API/InputEvent/dataTransfer)
    3.  [`inputType`](https://developer.mozilla.org/en-US/docs/Web/API/InputEvent/inputType)
    4.  [`isComposing`](https://developer.mozilla.org/en-US/docs/Web/API/InputEvent/isComposing)
4.  Methods
    1.  [`getTargetRanges()`](https://developer.mozilla.org/en-US/docs/Web/API/InputEvent/getTargetRanges)
5.  Inheritance:
    1.  [`UIEvent`](https://developer.mozilla.org/en-US/docs/Web/API/UIEvent)
    2.  [`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event)
6.  Related pages for DOM Events
    1.  [`CompositionEvent`](https://developer.mozilla.org/en-US/docs/Web/API/CompositionEvent)
    2.  [`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event)
    3.  [`EventListener`](https://developer.mozilla.org/en-US/docs/Web/API/EventListener)
    4.  [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)
    5.  [`FocusEvent`](https://developer.mozilla.org/en-US/docs/Web/API/FocusEvent)
    6.  [`KeyboardEvent`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent)
    7.  [`MouseEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent)
    8.  [`MouseScrollEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MouseScrollEvent)
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
-   [Terms](https://www.mozilla.org/about/legal/terms/mozilla)
-   [Privacy](https://www.mozilla.org/privacy/websites/)
-   [Cookies](https://www.mozilla.org/privacy/websites/#cookies)
