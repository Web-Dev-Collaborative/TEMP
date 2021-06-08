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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement" class="breadcrumb-penultimate"><span data-property="name">HTMLElement</span></a>
4.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/input_event" class="breadcrumb-current-page"><span data-property="name">HTMLElement: input event</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Examples](#examples)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

HTMLElement: input event
========================

The **`input`** event fires when the `value` of an [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input), [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select), or [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea) element has been changed. 

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/InputEvent"><code>InputEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oninput"><code>GlobalEventHandlers.oninput</code></a></td></tr></tbody></table>

The event also applies to elements with [`contenteditable`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/contentEditable "contenteditable") enabled, and to any element when [`designMode`](https://developer.mozilla.org/en-US/docs/Web/API/Document/designMode "designMode") is turned on. In the case of `contenteditable` and `designMode`, the event target is the *editing host*. If these properties apply to multiple elements, the editing host is the nearest ancestor element whose parent isn't editable.

For `<input>` elements with `type=checkbox` or `type=radio`, the `input` event should fire whenever a user toggles the control, per <a href="https://html.spec.whatwg.org/multipage/input.html#the-input-element:event-input-2" class="external">the HTML5 specification</a>. However, historically this has not always been the case. Check compatibility, or use the [`change`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/change_event "change") event instead for elements of these types.

**Note:** The `input` event is fired every time the `value` of the element changes. This is unlike the [`change`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/change_event "change") event, which only fires when the value is committed, such as by pressing the enter key, selecting a value from a list of options, and the like.

[Examples](#examples "Permalink to Examples")
---------------------------------------------

This example logs the value whenever you change the value of the [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element.

### [HTML](#html "Permalink to HTML")

    <input placeholder="Enter some text" name="name"/>
    <p id="values"></p>

### [JavaScript](#javascript "Permalink to JavaScript")

    const input = document.querySelector('input');
    const log = document.getElementById('values');

    input.addEventListener('input', updateValue);

    function updateValue(e) {
      log.textContent = e.target.value;
    }

### [Result](#result "Permalink to Result")

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/forms.html#event-input-input" class="external">HTML Living Standard<br />
<span class="small">The definition of 'input event' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#event-type-input" class="external">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'input event' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   Related events
    -   [`beforeinput`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/beforeinput_event "beforeinput")
    -   [`change`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/change_event "change")
    -   [`invalid`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/invalid_event "invalid")

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/htmlelement/input_event/index.html "Folder: en-us/web/api/htmlelement/input_event (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FHTMLElement%2Finput_event%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fhtmlelement%2Finput_event%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FHTMLElement%2Finput_event%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fhtmlelement%2Finput_event%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fcb20a8045f6cbdbd224b1068e46c8644470dd8c3%0A*+Document+last+modified%3A+2021-06-01T09%3A10%3A31.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22HTMLElement%3A+input+event%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Jun 1, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/input_event/contributors.txt)

Change your languageSelect your preferred language English (US)EspañolFrançais日本語한국어Português (do Brasil)中文 (简体)

Change language

#### Related Topics

1.  **[`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)**
2.  Properties
    1.  [`contentEditable`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/contentEditable)
    2.  [`contextMenu`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/contextMenu)
    3.  [`dir`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/dir)
    4.  [`enterKeyHint`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/enterKeyHint)
    5.  [`hidden`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/hidden)
    6.  [`innerText`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/innerText)
    7.  [`isContentEditable`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/isContentEditable)
    8.  [`lang`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/lang)
    9.  [`offsetHeight`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/offsetHeight)
    10. [`offsetLeft`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/offsetLeft)
    11. [`offsetParent`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/offsetParent)
    12. [`offsetTop`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/offsetTop)
    13. [`offsetWidth`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/offsetWidth)
    14. [`onabort`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onabort)
    15. [`onanimationcancel`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onanimationcancel)
    16. [`onanimationend`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onanimationend)
    17. [`onanimationiteration`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onanimationiteration)
    18. [`onauxclick`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onauxclick)
    19. [`onblur`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onblur)
    20. [`oncancel`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oncancel)
    21. [`oncanplay`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oncanplay)
    22. [`oncanplaythrough`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oncanplaythrough)
    23. [`onchange`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onchange)
    24. [`onclick`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onclick)
    25. [`onclose`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onclose)
    26. [`oncontextmenu`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oncontextmenu)
    27. [`oncopy`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/oncopy)
    28. [`oncuechange`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oncuechange)
    29. [`oncut`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/oncut)
    30. [`ondblclick`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ondblclick)
    31. [`ondurationchange`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ondurationchange)
    32. [`onended`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onended)
    33. [`onerror`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onerror)
    34. [`onfocus`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onfocus)
    35. [`onformdata`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onformdata)
    36. [`ongotpointercapture`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ongotpointercapture)
    37. [`oninput`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oninput)
    38. [`oninvalid`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oninvalid)
    39. [`onkeydown`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onkeydown)
    40. [`onkeypress`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onkeypress)
    41. [`onkeyup`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onkeyup)
    42. [`onload`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onload)
    43. [`onloadeddata`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onloadeddata)
    44. [`onloadedmetadata`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onloadedmetadata)
    45. [`onloadend`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onloadend)
    46. [`onloadstart`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onloadstart)
    47. [`onlostpointercapture`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onlostpointercapture)
    48. [`onmousedown`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmousedown)
    49. [`onmouseenter`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmouseenter)
    50. [`onmouseleave`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmouseleave)
    51. [`onmousemove`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmousemove)
    52. [`onmouseout`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmouseout)
    53. [`onmouseover`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmouseover)
    54. [`onmouseup`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmouseup)
    55. [`onpaste`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/onpaste)
    56. [`onpause`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpause)
    57. [`onplay`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onplay)
    58. [`onplaying`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onplaying)
    59. [`onpointercancel`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointercancel)
    60. [`onpointerdown`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointerdown)
    61. [`onpointerenter`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointerenter)
    62. [`onpointerleave`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointerleave)
    63. [`onpointermove`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointermove)
    64. [`onpointerout`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointerout)
    65. [`onpointerover`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointerover)
    66. [`onpointerup`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointerup)
    67. [`onreset`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onreset)
    68. [`onresize`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onresize)
    69. [`onscroll`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onscroll)
    70. [`onselect`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onselect)
    71. [`onselectionchange`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onselectionchange)
    72. [`onselectstart`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onselectstart)
    73. [`onsubmit`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onsubmit)
    74. [`ontouchcancel`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ontouchcancel)
    75. [`ontouchstart`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ontouchstart)
    76. [`ontransitioncancel`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ontransitioncancel)
    77. [`ontransitionend`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ontransitionend)
    78. [`onwheel`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onwheel)
    79. [`outerText`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/outerText)
    80. [`title`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/title)
3.  Methods
    1.  [`click()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/click)
4.  Events
    1.  [`animationcancel`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/animationcancel_event)
    2.  [`animationend`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/animationend_event)
    3.  [`animationiteration`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/animationiteration_event)
    4.  [`animationstart`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/animationstart_event)
    5.  [`beforeinput`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/beforeinput_event)
    6.  [`change`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/change_event)
    7.  [`gotpointercapture`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/gotpointercapture_event)
    8.  *`input`*
    9.  [`lostpointercapture`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/lostpointercapture_event)
    10. [`pointercancel`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/pointercancel_event)
    11. [`pointerdown`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/pointerdown_event)
    12. [`pointerenter`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/pointerenter_event)
    13. [`pointerleave`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/pointerleave_event)
    14. [`pointermove`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/pointermove_event)
    15. [`pointerout`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/pointerout_event)
    16. [`pointerover`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/pointerover_event)
    17. [`pointerup`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/pointerup_event)
    18. [`transitioncancel`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/transitioncancel_event)
    19. [`transitionend`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/transitionend_event)
    20. [`transitionrun`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/transitionrun_event)
    21. [`transitionstart`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/transitionstart_event)
5.  Inheritance:
    1.  [`Element`](https://developer.mozilla.org/en-US/docs/Web/API/Element)
    2.  [`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node)
    3.  [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)

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
