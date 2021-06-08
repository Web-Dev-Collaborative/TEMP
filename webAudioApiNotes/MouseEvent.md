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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent" class="breadcrumb-current-page"><span data-property="name">MouseEvent</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Constructor](#constructor)
-   [Properties](#properties)
-   [Constants](#constants)
-   [Methods](#methods)
-   [Example](#example)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

MouseEvent
==========

The `MouseEvent` interface represents events that occur due to the user interacting with a pointing device (such as a mouse). Common events using this interface include `click`, `dblclick`, `mouseup`, `mousedown`.

`MouseEvent` derives from [`UIEvent`](https://developer.mozilla.org/en-US/docs/Web/API/UIEvent), which in turn derives from [`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event). Though the [`MouseEvent.initMouseEvent()`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/initMouseEvent) method is kept for backward compatibility, creating of a `MouseEvent` object should be done using the [`MouseEvent()`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/MouseEvent "MouseEvent()") constructor.

Several more specific events are based on `MouseEvent`, including [`WheelEvent`](https://developer.mozilla.org/en-US/docs/Web/API/WheelEvent) and [`DragEvent`](https://developer.mozilla.org/en-US/docs/Web/API/DragEvent).

[Constructor](#constructor "Permalink to Constructor")
------------------------------------------------------

[`MouseEvent()`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/MouseEvent "MouseEvent()")  
Creates a `MouseEvent` object.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

*This interface also inherits properties of its parents, [`UIEvent`](https://developer.mozilla.org/en-US/docs/Web/API/UIEvent) and [`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event).*

[`MouseEvent.altKey`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/altKey) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns `true` if the alt key was down when the mouse event was fired.

[`MouseEvent.button`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/button) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
The button number that was pressed (if applicable) when the mouse event was fired.

[`MouseEvent.buttons`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/buttons) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
The buttons being depressed (if any) when the mouse event was fired.

[`MouseEvent.clientX`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/clientX) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
The X coordinate of the mouse pointer in local (DOM content) coordinates.

[`MouseEvent.clientY`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/clientY) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
The Y coordinate of the mouse pointer in local (DOM content) coordinates.

[`MouseEvent.ctrlKey`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/ctrlKey) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns `true` if the control key was down when the mouse event was fired.

[`MouseEvent.metaKey`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/metaKey) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns `true` if the meta key was down when the mouse event was fired.

[`MouseEvent.movementX`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/movementX) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
The X coordinate of the mouse pointer relative to the position of the last `mousemove` event.

[`MouseEvent.movementY`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/movementY) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
The Y coordinate of the mouse pointer relative to the position of the last `mousemove` event.

[`MouseEvent.offsetX`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/offsetX) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
The X coordinate of the mouse pointer relative to the position of the padding edge of the target node.

[`MouseEvent.offsetY`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/offsetY) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
The Y coordinate of the mouse pointer relative to the position of the padding edge of the target node.

[`MouseEvent.pageX`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/pageX) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
The X coordinate of the mouse pointer relative to the whole document.

[`MouseEvent.pageY`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/pageY) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
The Y coordinate of the mouse pointer relative to the whole document.

[`MouseEvent.region`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/region) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the id of the hit region affected by the event. If no hit region is affected, `null` is returned.

[`MouseEvent.relatedTarget`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/relatedTarget) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
The secondary target for the event, if there is one.

[`MouseEvent.screenX`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/screenX) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
The X coordinate of the mouse pointer in global (screen) coordinates.

[`MouseEvent.screenY`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/screenY) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
The Y coordinate of the mouse pointer in global (screen) coordinates.

[`MouseEvent.shiftKey`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/shiftKey) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns `true` if the shift key was down when the mouse event was fired.

[`MouseEvent.which`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/which) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
The button being pressed when the mouse event was fired.

<span class="page-not-created">`MouseEvent.mozPressure`</span> <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
The amount of pressure applied to a touch or tablet device when generating the event; this value ranges between `0.0` (minimum pressure) and `1.0` (maximum pressure). Instead of using this deprecated (and non-standard) property, you should instead use [`PointerEvent`](https://developer.mozilla.org/en-US/docs/Web/API/PointerEvent) and look at its [`pressure`](https://developer.mozilla.org/en-US/docs/Web/API/PointerEvent/pressure "pressure") property.

[`MouseEvent.mozInputSource`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/mozInputSource) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
The type of device that generated the event (one of the `MOZ_SOURCE_*` constants listed below). This lets you, for example, determine whether a mouse event was generated by an actual mouse or by a touch event (which might affect the degree of accuracy with which you interpret the coordinates associated with the event).

[`MouseEvent.webkitForce`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/webkitForce) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
The amount of pressure applied when clicking

[`MouseEvent.x`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/x) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Alias for [`MouseEvent.clientX`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/clientX).

[`MouseEvent.y`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/y) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Alias for [`MouseEvent.clientY`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/clientY)

[Constants](#constants "Permalink to Constants")
------------------------------------------------

[`MouseEvent.WEBKIT_FORCE_AT_MOUSE_DOWN`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/WEBKIT_FORCE_AT_MOUSE_DOWN) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Minimum force necessary for a normal click

[`MouseEvent.WEBKIT_FORCE_AT_FORCE_MOUSE_DOWN`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/WEBKIT_FORCE_AT_FORCE_MOUSE_DOWN) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Minimum force necessary for a force click

[Methods](#methods "Permalink to Methods")
------------------------------------------

*This interface also inherits methods of its parents, [`UIEvent`](https://developer.mozilla.org/en-US/docs/Web/API/UIEvent) and [`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event).*

[`MouseEvent.getModifierState()`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/getModifierState)  
Returns the current state of the specified modifier key. See [`KeyboardEvent.getModifierState()`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/getModifierState "KeyboardEvent.getModifierState()") for details.

[`MouseEvent.initMouseEvent()`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/initMouseEvent)   
Initializes the value of a `MouseEvent` created. If the event has already being dispatched, this method does nothing.

[Example](#example "Permalink to Example")
------------------------------------------

This example demonstrates simulating a click (programmatically generating a click event) on a checkbox using DOM methods. Event state (canceled or not) is then determined with the return value of method [`EventTarget.dispatchEvent()`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/dispatchEvent "EventTarget.dispatchEvent()").

### [HTML](#html "Permalink to HTML")

    <p><label><input type="checkbox" id="checkbox"> Checked</label>
    <p><button id="button">Click me</button>

### [JavaScript](#javascript "Permalink to JavaScript")

    function simulateClick() {
      var evt = new MouseEvent("click", {
        bubbles: true,
        cancelable: true,
        view: window
      });
      var cb = document.getElementById("checkbox"); //element to click on
      var canceled = !cb.dispatchEvent(evt);
      if(canceled) {
        // A handler called preventDefault
        alert("canceled");
      } else {
        // None of the handlers called preventDefault
        alert("not canceled");
      }
    }
    document.getElementById("button").addEventListener('click', simulateClick);

### [Result](#result "Permalink to Result")

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#extensions-to-the-mouseevent-interface" class="external">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'MouseEvent' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Redefines <code>MouseEvent</code> from long to double. This means that a <code>PointerEvent</code> whose <code>pointerType</code> is mouse will be a double.</td></tr><tr class="even"><td><a href="https://w3c.github.io/pointerlock/#extensions-to-the-mouseevent-interface" class="external">Pointer Lock<br />
<span class="small">The definition of 'MouseEvent' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>From <a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/" class="external" title="The &#39;Document Object Model (DOM) Level 3 Events Specification&#39; specification">Document Object Model (DOM) Level 3 Events Specification</a>, added <code>movementX</code> and <code>movementY</code> properties.</td></tr><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#extensions-to-the-mouseevent-interface" class="external">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'MouseEvent' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>From <a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/" class="external" title="The &#39;Document Object Model (DOM) Level 3 Events Specification&#39; specification">Document Object Model (DOM) Level 3 Events Specification</a>, added <code>offsetX</code> and <code>offsetY</code>, <code>pageX</code> and <code>pageY</code>, <code>x</code>, and <code>y</code> properties. Redefined screen, page, client, and coordinate (x and y) properties as <code>double</code> from <code>long</code>.</td></tr><tr class="even"><td><a href="https://w3c.github.io/uievents/#interface-mouseevent" class="external">UI Events<br />
<span class="small">The definition of 'MouseEvent' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#events-mouseevents" class="external">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'MouseEvent' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>From <a href="https://www.w3.org/TR/DOM-Level-2-Events/events.html" class="external" title="The &#39;Document Object Model (DOM) Level 2 Events Specification&#39; specification">Document Object Model (DOM) Level 2 Events Specification</a>, added the <code>MouseEvent()</code> constructor, the <code>getModifierState()</code> method and the <code>buttons</code> property.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Events/events.html#Events-MouseEvent" class="external">Document Object Model (DOM) Level 2 Events Specification<br />
<span class="small">The definition of 'MouseEvent' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   Its direct parent, [`UIEvent`](https://developer.mozilla.org/en-US/docs/Web/API/UIEvent).
-   [`PointerEvent`](https://developer.mozilla.org/en-US/docs/Web/API/PointerEvent): For advanced pointer events, including multi-touch

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/mouseevent/index.html "Folder: en-us/web/api/mouseevent (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FMouseEvent%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fmouseevent%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FMouseEvent%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fmouseevent%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F5737ba49f3f0c3fc7587d329f1362a7a66afdd80%0A*+Document+last+modified%3A+2021-05-31T16%3A58%3A42.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22MouseEvent%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/contributors.txt)

Change your languageSelect your preferred language English (US)DeutschEspañolFrançais日本語한국어Português (do Brasil)Русский中文 (简体)正體中文 (繁體)

Change language

#### Related Topics

1.  **[`MouseEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent)**
2.  Constructor
    1.  [`MouseEvent()`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/MouseEvent)
3.  Properties
    1.  [`altKey`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/altKey)
    2.  [`button`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/button)
    3.  [`buttons`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/buttons)
    4.  [`clientX`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/clientX)
    5.  [`clientY`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/clientY)
    6.  [`ctrlKey`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/ctrlKey)
    7.  [`metaKey`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/metaKey)
    8.  [`movementX`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/movementX)
    9.  [`movementY`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/movementY)
    10. [`mozInputSource`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/mozInputSource)
    11. [`offsetX`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/offsetX)
    12. [`offsetY`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/offsetY)
    13. [`pageX`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/pageX)
    14. [`pageY`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/pageY)
    15. [`region`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/region)
    16. [`relatedTarget`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/relatedTarget)
    17. [`screenX`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/screenX)
    18. [`screenY`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/screenY)
    19. [`shiftKey`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/shiftKey)
    20. [`WEBKIT_FORCE_AT_FORCE_MOUSE_DOWN`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/WEBKIT_FORCE_AT_FORCE_MOUSE_DOWN)
    21. [`WEBKIT_FORCE_AT_MOUSE_DOWN`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/WEBKIT_FORCE_AT_MOUSE_DOWN)
    22. [`webkitForce`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/webkitForce)
    23. [`which`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/which)
    24. [`x`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/x)
    25. [`y`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/y)
4.  Methods
    1.  [`getModifierState()`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/getModifierState)
    2.  [`initMouseEvent()`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/initMouseEvent)
5.  Inheritance:
    1.  [`UIEvent`](https://developer.mozilla.org/en-US/docs/Web/API/UIEvent)
    2.  [`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event)
6.  Related pages for DOM Events
    1.  [`CompositionEvent`](https://developer.mozilla.org/en-US/docs/Web/API/CompositionEvent)
    2.  [`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event)
    3.  [`EventListener`](https://developer.mozilla.org/en-US/docs/Web/API/EventListener)
    4.  [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)
    5.  [`FocusEvent`](https://developer.mozilla.org/en-US/docs/Web/API/FocusEvent)
    6.  [`InputEvent`](https://developer.mozilla.org/en-US/docs/Web/API/InputEvent)
    7.  [`KeyboardEvent`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent)
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

#### Mozilla

-   <a href="https://twitter.com/mozilla" class="social-icon twitter"><span class="visually-hidden">Mozilla on Twitter</span></a>
-   <a href="https://www.instagram.com/mozillagram/" class="social-icon instagram"><span class="visually-hidden">Mozilla on Instagram</span></a>

© 2005-2021 Mozilla and individual contributors. Content is available under [these licenses](https://developer.mozilla.org/docs/MDN/About#Copyrights_and_licenses).

-   [Terms](https://www.mozilla.org/about/legal/terms/mozilla)
-   [Privacy](https://www.mozilla.org/privacy/websites/)
-   [Cookies](https://www.mozilla.org/privacy/websites/#cookies)
