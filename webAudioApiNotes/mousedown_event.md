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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/Element" class="breadcrumb-penultimate"><span data-property="name">Element</span></a>
4.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/mousedown_event" class="breadcrumb-current-page"><span data-property="name">Element: mousedown event</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Examples](#examples)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

Element: mousedown event
========================

<span class="seoSummary">The **`mousedown`** event is fired at an [`Element`](https://developer.mozilla.org/en-US/docs/Web/API/Element) when a pointing device button is pressed while the pointer is inside the element.</span>

**Note:** This differs from the [`click`](https://developer.mozilla.org/en-US/docs/Web/API/Element/click_event "click") event in that `click` is fired after a full click action occurs; that is, the mouse button is pressed and released while the pointer remains inside the same element. `mousedown` is fired the moment the button is initially pressed.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>Yes</td></tr><tr class="odd"><td>Interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent"><code>MouseEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmousedown" title="onmousedown"><code>onmousedown</code></a></td></tr></tbody></table>

[Examples](#examples "Permalink to Examples")
---------------------------------------------

The following example uses the [`mousedown`](https://developer.mozilla.org/en-US/docs/Web/API/Element/mousedown_event "mousedown"), `mousemove`, and [`mouseup`](https://developer.mozilla.org/en-US/docs/Web/API/Element/mouseup_event "mouseup") events to allow the user to draw on an HTML5 [canvas](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API). Its functionality is simple: the thickness of the line is set to 1, and the color is always black.

When the page loads, constants `myPics` and `context` are created to store a reference to the canvas and the 2d context we will use to draw.

Drawing begins when the `mousedown` event fires. First we store the x and y coordinates of the mouse pointer in the variables `x` and `y`, and then set `isDrawing` to true.

As the mouse moves over the page, the `mousemove` event fires. If `isDrawing` is true, the event handler calls the `drawLine` function to draw a line from the stored `x` and `y` values to the current location.

When the `drawLine()` function returns, we adjust the coordinates and then save them in `x` and `y`.

The `mouseup` event draws the final line segment, sets `x` and `y` to `0`, and stops further drawing by setting `isDrawing` to `false`.

### [HTML](#html "Permalink to HTML")

    <h1>Drawing with mouse events</h1>
    <canvas id="myPics" width="560" height="360"></canvas>

### [CSS](#css "Permalink to CSS")

    canvas {
      border: 1px solid black;
      width: 560px;
      height: 360px;
    }

### [JavaScript](#javascript "Permalink to JavaScript")

    // When true, moving the mouse draws on the canvas
    let isDrawing = false;
    let x = 0;
    let y = 0;

    const myPics = document.getElementById('myPics');
    const context = myPics.getContext('2d');

    // event.offsetX, event.offsetY gives the (x,y) offset from the edge of the canvas.

    // Add the event listeners for mousedown, mousemove, and mouseup
    myPics.addEventListener('mousedown', e => {
      x = e.offsetX;
      y = e.offsetY;
      isDrawing = true;
    });

    myPics.addEventListener('mousemove', e => {
      if (isDrawing === true) {
        drawLine(context, x, y, e.offsetX, e.offsetY);
        x = e.offsetX;
        y = e.offsetY;
      }
    });

    window.addEventListener('mouseup', e => {
      if (isDrawing === true) {
        drawLine(context, x, y, e.offsetX, e.offsetY);
        x = 0;
        y = 0;
        isDrawing = false;
      }
    });

    function drawLine(context, x1, y1, x2, y2) {
      context.beginPath();
      context.strokeStyle = 'black';
      context.lineWidth = 1;
      context.moveTo(x1, y1);
      context.lineTo(x2, y2);
      context.stroke();
      context.closePath();
    }

### [Result](#result "Permalink to Result")

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/uievents/#event-type-mousedown" class="external">UI Events<br />
<span class="small">The definition of 'mousedown' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#event-type-mousedown" class="external">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'mousedown' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Introduction to events](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events)
-   [`mouseup`](https://developer.mozilla.org/en-US/docs/Web/API/Element/mouseup_event "mouseup")
-   [`mousemove`](https://developer.mozilla.org/en-US/docs/Web/API/Element/mousemove_event "mousemove")
-   [`click`](https://developer.mozilla.org/en-US/docs/Web/API/Element/click_event "click")
-   [`dblclick`](https://developer.mozilla.org/en-US/docs/Web/API/Element/dblclick_event "dblclick")
-   [`mouseover`](https://developer.mozilla.org/en-US/docs/Web/API/Element/mouseover_event "mouseover")
-   [`mouseout`](https://developer.mozilla.org/en-US/docs/Web/API/Element/mouseout_event "mouseout")
-   [`mouseenter`](https://developer.mozilla.org/en-US/docs/Web/API/Element/mouseenter_event "mouseenter")
-   [`mouseleave`](https://developer.mozilla.org/en-US/docs/Web/API/Element/mouseleave_event "mouseleave")
-   [`contextmenu`](https://developer.mozilla.org/en-US/docs/Web/API/Element/contextmenu_event "contextmenu")

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/element/mousedown_event/index.html "Folder: en-us/web/api/element/mousedown_event (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FElement%2Fmousedown_event%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Felement%2Fmousedown_event%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FElement%2Fmousedown_event%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Felement%2Fmousedown_event%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F4f1675a38205aeb5f7336aba793ce8e9a1cd1d5d%0A*+Document+last+modified%3A+2021-06-01T10%3A08%3A01.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22Element%3A+mousedown+event%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Jun 1, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/Element/mousedown_event/contributors.txt)

Change your languageSelect your preferred language English (US)EspañolFrançais日本語Português (do Brasil)Русский中文 (简体)

Change language

#### Related Topics

1.  **[`Element`](https://developer.mozilla.org/en-US/docs/Web/API/Element)**
2.  Properties
    1.  [`ariaAtomic`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaAtomic)
    2.  [`ariaAutoComplete`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaAutoComplete)
    3.  [`ariaBusy`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaBusy)
    4.  [`ariaChecked`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaChecked)
    5.  [`ariaColCount`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaColCount)
    6.  [`ariaColIndex`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaColIndex)
    7.  [`ariaColIndexText`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaColIndexText)
    8.  [`ariaColSpan`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaColSpan)
    9.  [`ariaCurrent`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaCurrent)
    10. [`ariaDescription`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaDescription)
    11. [`ariaDisabled`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaDisabled)
    12. [`ariaExpanded`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaExpanded)
    13. [`ariaHasPopup`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaHasPopup)
    14. [`ariaHidden`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaHidden)
    15. [`ariaKeyShortcuts`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaKeyShortcuts)
    16. [`ariaLabel`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaLabel)
    17. [`ariaLevel`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaLevel)
    18. [`ariaLive`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaLive)
    19. [`ariaModal`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaModal)
    20. [`ariaMultiline`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaMultiline)
    21. [`ariaMultiSelectable`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaMultiSelectable)
    22. [`ariaOrientation`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaOrientation)
    23. [`ariaPlaceholder`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaPlaceholder)
    24. [`ariaPosInSet`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaPosInSet)
    25. [`ariaPressed`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaPressed)
    26. [`ariaReadOnly`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaReadOnly)
    27. [`ariaRelevant`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaRelevant)
    28. [`ariaRequired`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaRequired)
    29. [`ariaRoleDescription`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaRoleDescription)
    30. [`ariaRowCount`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaRowCount)
    31. [`ariaRowIndex`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaRowIndex)
    32. [`ariaRowIndexText`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaRowIndexText)
    33. [`ariaRowSpan`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaRowSpan)
    34. [`ariaSelected`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaSelected)
    35. [`ariaSetSize`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaSetSize)
    36. [`ariaSort`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaSort)
    37. [`ariaValueMax`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaValueMax)
    38. [`ariaValueMin`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaValueMin)
    39. [`ariaValueNow`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaValueNow)
    40. [`ariaValueText`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaValueText)
    41. [`attributes`](https://developer.mozilla.org/en-US/docs/Web/API/Element/attributes)
    42. [`childElementCount`](https://developer.mozilla.org/en-US/docs/Web/API/Element/childElementCount)
    43. [`children`](https://developer.mozilla.org/en-US/docs/Web/API/Element/children)
    44. [`classList`](https://developer.mozilla.org/en-US/docs/Web/API/Element/classList)
    45. [`className`](https://developer.mozilla.org/en-US/docs/Web/API/Element/className)
    46. [`clientHeight`](https://developer.mozilla.org/en-US/docs/Web/API/Element/clientHeight)
    47. [`clientLeft`](https://developer.mozilla.org/en-US/docs/Web/API/Element/clientLeft)
    48. [`clientTop`](https://developer.mozilla.org/en-US/docs/Web/API/Element/clientTop)
    49. [`clientWidth`](https://developer.mozilla.org/en-US/docs/Web/API/Element/clientWidth)
    50. [`currentStyle`](https://developer.mozilla.org/en-US/docs/Web/API/Element/currentStyle)
    51. [`Element: assignedSlot`](https://developer.mozilla.org/en-US/docs/Web/API/Element/assignedSlot)
    52. [`firstElementChild`](https://developer.mozilla.org/en-US/docs/Web/API/Element/firstElementChild)
    53. [`id`](https://developer.mozilla.org/en-US/docs/Web/API/Element/id)
    54. [`innerHTML`](https://developer.mozilla.org/en-US/docs/Web/API/Element/innerHTML)
    55. [`lastElementChild`](https://developer.mozilla.org/en-US/docs/Web/API/Element/lastElementChild)
    56. [`localName`](https://developer.mozilla.org/en-US/docs/Web/API/Element/localName)
    57. [`namespaceURI`](https://developer.mozilla.org/en-US/docs/Web/API/Element/namespaceURI)
    58. [`nextElementSibling`](https://developer.mozilla.org/en-US/docs/Web/API/Element/nextElementSibling)
    59. [`onfullscreenchange`](https://developer.mozilla.org/en-US/docs/Web/API/Element/onfullscreenchange)
    60. [`onfullscreenerror`](https://developer.mozilla.org/en-US/docs/Web/API/Element/onfullscreenerror)
    61. [`openOrClosedShadowRoot`](https://developer.mozilla.org/en-US/docs/Web/API/Element/openOrClosedShadowRoot)
    62. [`outerHTML`](https://developer.mozilla.org/en-US/docs/Web/API/Element/outerHTML)
    63. [`part`](https://developer.mozilla.org/en-US/docs/Web/API/Element/part)
    64. [`prefix`](https://developer.mozilla.org/en-US/docs/Web/API/Element/prefix)
    65. [`previousElementSibling`](https://developer.mozilla.org/en-US/docs/Web/API/Element/previousElementSibling)
    66. [`runtimeStyle`](https://developer.mozilla.org/en-US/docs/Web/API/Element/runtimeStyle)
    67. [`scrollHeight`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollHeight)
    68. [`scrollLeft`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollLeft)
    69. [`scrollLeftMax`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollLeftMax)
    70. [`scrollTop`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollTop)
    71. [`scrollTopMax`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollTopMax)
    72. [`scrollWidth`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollWidth)
    73. [`shadowRoot`](https://developer.mozilla.org/en-US/docs/Web/API/Element/shadowRoot)
    74. [`slot`](https://developer.mozilla.org/en-US/docs/Web/API/Element/slot)
    75. [`tagName`](https://developer.mozilla.org/en-US/docs/Web/API/Element/tagName)
3.  Methods
    1.  [`after()`](https://developer.mozilla.org/en-US/docs/Web/API/ChildNode/after)
    2.  [`animate()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/animate)
    3.  [`append()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/append)
    4.  [`attachShadow()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/attachShadow)
    5.  [`before()`](https://developer.mozilla.org/en-US/docs/Web/API/ChildNode/before)
    6.  [`closest()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/closest)
    7.  [`computedStyleMap()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/computedStyleMap)
    8.  [`createShadowRoot()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/createShadowRoot)
    9.  [`getAnimations()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/getAnimations)
    10. [`getAttribute()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/getAttribute)
    11. [`getAttributeNames()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/getAttributeNames)
    12. [`getAttributeNode()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/getAttributeNode)
    13. [`getAttributeNodeNS()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/getAttributeNodeNS)
    14. [`getAttributeNS()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/getAttributeNS)
    15. [`getBoundingClientRect()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/getBoundingClientRect)
    16. [`getClientRects()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/getClientRects)
    17. [`getElementsByClassName()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/getElementsByClassName)
    18. [`getElementsByTagName()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/getElementsByTagName)
    19. [`getElementsByTagNameNS()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/getElementsByTagNameNS)
    20. [`hasAttribute()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/hasAttribute)
    21. [`hasAttributeNS()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/hasAttributeNS)
    22. [`hasAttributes()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/hasAttributes)
    23. [`hasPointerCapture()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/hasPointerCapture)
    24. [`insertAdjacentElement()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/insertAdjacentElement)
    25. [`insertAdjacentHTML()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/insertAdjacentHTML)
    26. [`insertAdjacentText()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/insertAdjacentText)
    27. [`matches()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/matches)
    28. [`msZoomTo()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/msZoomTo)
    29. [`prepend()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/prepend)
    30. [`querySelector()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/querySelector)
    31. [`querySelectorAll()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/querySelectorAll)
    32. [`releasePointerCapture()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/releasePointerCapture)
    33. [`remove()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/remove)
    34. [`removeAttribute()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/removeAttribute)
    35. [`removeAttributeNode()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/removeAttributeNode)
    36. [`removeAttributeNS()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/removeAttributeNS)
    37. [`replaceChildren()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/replaceChildren)
    38. [`replaceWith()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/replaceWith)
    39. [`requestFullscreen()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/requestFullScreen)
    40. [`requestPointerLock()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/requestPointerLock)
    41. [`scroll()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scroll)
    42. [`scrollBy()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollBy)
    43. [`scrollIntoView()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollIntoView)
    44. [`scrollIntoViewIfNeeded()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollIntoViewIfNeeded)
    45. [`scrollTo()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollTo)
    46. [`setAttribute()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/setAttribute)
    47. [`setAttributeNode()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/setAttributeNode)
    48. [`setAttributeNodeNS()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/setAttributeNodeNS)
    49. [`setAttributeNS()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/setAttributeNS)
    50. [`setCapture()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/setCapture)
    51. [`setPointerCapture()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/setPointerCapture)
    52. [`toggleAttribute()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/toggleAttribute)
4.  Events
    1.  [`afterscriptexecute`](https://developer.mozilla.org/en-US/docs/Web/API/Element/afterscriptexecute_event)
    2.  [`auxclick`](https://developer.mozilla.org/en-US/docs/Web/API/Element/auxclick_event)
    3.  [`blur`](https://developer.mozilla.org/en-US/docs/Web/API/Element/blur_event)
    4.  [`click`](https://developer.mozilla.org/en-US/docs/Web/API/Element/click_event)
    5.  [`compositionend`](https://developer.mozilla.org/en-US/docs/Web/API/Element/compositionend_event)
    6.  [`compositionstart`](https://developer.mozilla.org/en-US/docs/Web/API/Element/compositionstart_event)
    7.  [`compositionupdate`](https://developer.mozilla.org/en-US/docs/Web/API/Element/compositionupdate_event)
    8.  [`contextmenu`](https://developer.mozilla.org/en-US/docs/Web/API/Element/contextmenu_event)
    9.  [`copy`](https://developer.mozilla.org/en-US/docs/Web/API/Element/copy_event)
    10. [`cut`](https://developer.mozilla.org/en-US/docs/Web/API/Element/cut_event)
    11. [`dblclick`](https://developer.mozilla.org/en-US/docs/Web/API/Element/dblclick_event)
    12. [`DOMActivate`](https://developer.mozilla.org/en-US/docs/Web/API/Element/DOMActivate_event)
    13. [`DOMMouseScroll`](https://developer.mozilla.org/en-US/docs/Web/API/Element/DOMMouseScroll_event)
    14. [`error`](https://developer.mozilla.org/en-US/docs/Web/API/Element/error_event)
    15. [`focus`](https://developer.mozilla.org/en-US/docs/Web/API/Element/focus_event)
    16. [`focusin`](https://developer.mozilla.org/en-US/docs/Web/API/Element/focusin_event)
    17. [`focusout`](https://developer.mozilla.org/en-US/docs/Web/API/Element/focusout_event)
    18. [`fullscreenchange`](https://developer.mozilla.org/en-US/docs/Web/API/Element/fullscreenchange_event)
    19. [`fullscreenerror`](https://developer.mozilla.org/en-US/docs/Web/API/Element/fullscreenerror_event)
    20. [`gesturechange`](https://developer.mozilla.org/en-US/docs/Web/API/Element/gesturechange_event)
    21. [`gestureend`](https://developer.mozilla.org/en-US/docs/Web/API/Element/gestureend_event)
    22. [`gesturestart`](https://developer.mozilla.org/en-US/docs/Web/API/Element/gesturestart_event)
    23. [`keydown`](https://developer.mozilla.org/en-US/docs/Web/API/Element/keydown_event)
    24. [`keypress`](https://developer.mozilla.org/en-US/docs/Web/API/Element/keypress_event)
    25. [`keyup`](https://developer.mozilla.org/en-US/docs/Web/API/Element/keyup_event)
    26. *`mousedown`*
    27. [`mouseenter`](https://developer.mozilla.org/en-US/docs/Web/API/Element/mouseenter_event)
    28. [`mouseleave`](https://developer.mozilla.org/en-US/docs/Web/API/Element/mouseleave_event)
    29. [`mousemove`](https://developer.mozilla.org/en-US/docs/Web/API/Element/mousemove_event)
    30. [`mouseout`](https://developer.mozilla.org/en-US/docs/Web/API/Element/mouseout_event)
    31. [`mouseover`](https://developer.mozilla.org/en-US/docs/Web/API/Element/mouseover_event)
    32. [`mouseup`](https://developer.mozilla.org/en-US/docs/Web/API/Element/mouseup_event)
    33. [`mousewheel`](https://developer.mozilla.org/en-US/docs/Web/API/Element/mousewheel_event)
    34. [`MozMousePixelScroll`](https://developer.mozilla.org/en-US/docs/Web/API/Element/MozMousePixelScroll)
    35. [`msContentZoom`](https://developer.mozilla.org/en-US/docs/Web/API/Element/msContentZoom_event)
    36. [`MSGestureChange`](https://developer.mozilla.org/en-US/docs/Web/API/Element/MSGestureChange_event)
    37. [`MSGestureEnd`](https://developer.mozilla.org/en-US/docs/Web/API/Element/MSGestureEnd_event)
    38. [`MSGestureHold`](https://developer.mozilla.org/en-US/docs/Web/API/Element/MSGestureHold_event)
    39. [`MSGestureStart`](https://developer.mozilla.org/en-US/docs/Web/API/Element/MSGestureStart_event)
    40. [`MSGestureTap`](https://developer.mozilla.org/en-US/docs/Web/API/Element/MSGestureTap_event)
    41. [`MSInertiaStart`](https://developer.mozilla.org/en-US/docs/Web/API/Element/MSInertiaStart_event)
    42. [`MSManipulationStateChanged`](https://developer.mozilla.org/en-US/docs/Web/API/Element/MSManipulationStateChanged_event)
    43. [`overflow`](https://developer.mozilla.org/en-US/docs/Web/API/Element/overflow_event)
    44. [`paste`](https://developer.mozilla.org/en-US/docs/Web/API/Element/paste_event)
    45. [`scroll`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scroll_event)
    46. [`select`](https://developer.mozilla.org/en-US/docs/Web/API/Element/select_event)
    47. [`show`](https://developer.mozilla.org/en-US/docs/Web/API/Element/show_event)
    48. [`touchcancel`](https://developer.mozilla.org/en-US/docs/Web/API/Element/touchcancel_event)
    49. [`touchend`](https://developer.mozilla.org/en-US/docs/Web/API/Element/touchend_event)
    50. [`touchmove`](https://developer.mozilla.org/en-US/docs/Web/API/Element/touchmove_event)
    51. [`touchstart`](https://developer.mozilla.org/en-US/docs/Web/API/Element/touchstart_event)
    52. [`underflow`](https://developer.mozilla.org/en-US/docs/Web/API/Element/underflow_event)
    53. [`webkitmouseforcechanged`](https://developer.mozilla.org/en-US/docs/Web/API/Element/webkitmouseforcechanged_event)
    54. [`webkitmouseforcedown`](https://developer.mozilla.org/en-US/docs/Web/API/Element/webkitmouseforcedown_event)
    55. [`webkitmouseforceup`](https://developer.mozilla.org/en-US/docs/Web/API/Element/webkitmouseforceup_event)
    56. [`webkitmouseforcewillbegin`](https://developer.mozilla.org/en-US/docs/Web/API/Element/webkitmouseforcewillbegin_event)
    57. [`wheel`](https://developer.mozilla.org/en-US/docs/Web/API/Element/wheel_event)
5.  Inheritance:
    1.  [`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node)
    2.  [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)

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
