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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement" class="breadcrumb-current-page"><span data-property="name">HTMLElement</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Properties](#properties)
-   [Methods](#methods)
-   [Events](#events)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

HTMLElement
===========

The **`HTMLElement`** interface represents any [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML) element. Some elements directly implement this interface, while others implement it via an interface that inherits it.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

*Inherits properties from its parent, [`Element`](https://developer.mozilla.org/en-US/docs/Web/API/Element), and implements those from <span class="page-not-created">`DocumentAndElementEventHandlers`</span>, [`ElementCSSInlineStyle`](https://developer.mozilla.org/en-US/docs/Web/API/ElementCSSInlineStyle), [`GlobalEventHandlers`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers), [`HTMLOrForeignElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOrForeignElement) and <span class="page-not-created">`TouchEventHandlers`</span>.*

[`HTMLElement.accessKey`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/accessKey)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) representing the access key assigned to the element.

[`HTMLElement.accessKeyLabel`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/accessKeyLabel) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) containing the element's assigned access key.

[`HTMLElement.contentEditable`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/contentEditable)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString), where a value of `true` means the element is editable and a value of `false` means it isn't.

[`HTMLElement.isContentEditable`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/isContentEditable) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that indicates whether or not the content of the element can be edited.

[`HTMLElement.contextMenu`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/contextMenu)   
Is a [`HTMLMenuElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMenuElement) representing the contextual menu associated with the element. It may be `null`.

[`HTMLOrForeignElement.dataset`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOrForeignElement/dataset) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`DOMStringMap`](https://developer.mozilla.org/en-US/docs/Web/API/DOMStringMap) with which script can read and write the element's [custom data attributes](https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto/Use_data_attributes) (`data-*`) .

[`HTMLElement.dir`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/dir)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString), reflecting the `dir` global attribute, representing the directionality of the element. Possible values are `"ltr"`, `"rtl"`, and `"auto"`.

<span class="page-not-created">`HTMLElement.draggable`</span>  
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating if the element can be dragged.

[`HTMLElement.enterkeyhint`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/enterKeyHint)  
Is a <span class="page-not-created">`DOMString`</span> defining what action label (or icon) to present for the enter key on virtual keyboards.

[`HTMLElement.hidden`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/hidden)  
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating if the element is hidden or not.

[`HTMLElement.inert`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/inert)  
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the user agent must act as though the given node is absent for the purposes of user interaction events, in-page text searches ("find in page"), and text selection.

[`HTMLElement.innerText`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/innerText)  
Represents the "rendered" text content of a node and its descendants. As a getter, it approximates the text the user would get if they highlighted the contents of the element with the cursor and then copied it to the clipboard.

<span class="page-not-created">`HTMLElement.itemScope`</span>   
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) representing the item scope.

<span class="page-not-created">`HTMLElement.itemType`</span> <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a <span class="page-not-created">`DOMSettableTokenList`</span>…

<span class="page-not-created">`HTMLElement.itemId`</span>   
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) representing the item ID.

<span class="page-not-created">`HTMLElement.itemRef`</span> <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a <span class="page-not-created">`DOMSettableTokenList`</span>…

<span class="page-not-created">`HTMLElement.itemProp`</span> <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a <span class="page-not-created">`DOMSettableTokenList`</span>…

<span class="page-not-created">`HTMLElement.itemValue`</span>   
Returns a [`Object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object) representing the item value.

[`HTMLElement.lang`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/lang)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) representing the language of an element's attributes, text, and element contents.

<span class="page-not-created">`HTMLElement.noModule`</span>  
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether an import script can be executed in user agents that support module scripts.

[`HTMLOrForeignElement.nonce`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOrForeignElement/nonce)  
Returns the cryptographic number used once that is used by Content Security Policy to determine whether a given fetch will be allowed to proceed.

[`HTMLElement.offsetHeight`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/offsetHeight) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a `double` containing the height of an element, relative to the layout.

[`HTMLElement.offsetLeft`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/offsetLeft) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a `double`, the distance from this element's left border to its `offsetParent`'s left border.

[`HTMLElement.offsetParent`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/offsetParent) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`Element`](https://developer.mozilla.org/en-US/docs/Web/API/Element) that is the element from which all offset calculations are currently computed.

[`HTMLElement.offsetTop`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/offsetTop) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a `double`, the distance from this element's top border to its `offsetParent`'s top border.

[`HTMLElement.offsetWidth`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/offsetWidth) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a `double` containing the width of an element, relative to the layout.

<span class="page-not-created">`HTMLElement.properties`</span> <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a <span class="page-not-created">`HTMLPropertiesCollection`</span>…

<span class="page-not-created">`HTMLElement.spellcheck`</span>  
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that controls [spell-checking](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/spellcheck). It is present on all HTML elements, though it doesn't have an effect on all of them.

[`ElementCSSInlineStyle.style`](https://developer.mozilla.org/en-US/docs/Web/API/ElementCSSInlineStyle/style)  
Is a [`CSSStyleDeclaration`](https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleDeclaration), an object representing the declarations of an element's style attributes.

[`HTMLOrForeignElement.tabIndex`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOrForeignElement/tabIndex)  
Is a `long` representing the position of the element in the tabbing order.

[`HTMLElement.title`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/title)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) containing the text that appears in a popup box when mouse is over the element.

<span class="page-not-created">`HTMLElement.translate`</span>   
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) representing the translation.

### [Event handlers](#event_handlers "Permalink to Event handlers")

Most event handler properties, of the form `onXYZ`, are defined on the <span class="page-not-created">`DocumentAndElementEventHandlers`</span>, [`GlobalEventHandlers`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers) or <span class="page-not-created">`TouchEventHandlers`</span> interfaces and implemented by `HTMLElement`. In addition, the following handlers are specific to `HTMLElement`.

[`HTMLElement.oncopy`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/oncopy)   
Returns the event handling code for the `copy` event (<a href="https://bugzilla.mozilla.org/show_bug.cgi?id=280959" class="external">bug 280959</a>).

[`HTMLElement.oncut`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/oncut)   
Returns the event handling code for the `cut` event (<a href="https://bugzilla.mozilla.org/show_bug.cgi?id=280959" class="external">bug 280959</a>).

[`HTMLElement.onpaste`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/onpaste)   
Returns the event handling code for the `paste` event (<a href="https://bugzilla.mozilla.org/show_bug.cgi?id=280959" class="external">bug 280959</a>).

<span class="page-not-created">`TouchEventHandlers.ontouchstart`</span>   
Returns the event handling code for the [`touchstart`](https://developer.mozilla.org/en-US/docs/Web/API/Element/touchstart_event "touchstart") event.

<span class="page-not-created">`TouchEventHandlers.ontouchend`</span>   
Returns the event handling code for the [`touchend`](https://developer.mozilla.org/en-US/docs/Web/API/Element/touchend_event "touchend") event.

<span class="page-not-created">`TouchEventHandlers.ontouchmove`</span>   
Returns the event handling code for the [`touchmove`](https://developer.mozilla.org/en-US/docs/Web/API/Element/touchmove_event "touchmove") event.

<span class="page-not-created">`TouchEventHandlers.ontouchenter`</span>   
Returns the event handling code for the `touchenter` event.

<span class="page-not-created">`TouchEventHandlers.ontouchleave`</span>   
Returns the event handling code for the `touchleave` event.

<span class="page-not-created">`TouchEventHandlers.ontouchcancel`</span>   
Returns the event handling code for the [`touchcancel`](https://developer.mozilla.org/en-US/docs/Web/API/Element/touchcancel_event "touchcancel") event.

[Methods](#methods "Permalink to Methods")
------------------------------------------

*Inherits methods from its parent, [`Element`](https://developer.mozilla.org/en-US/docs/Web/API/Element), and implements those from <span class="page-not-created">`DocumentAndElementEventHandlers`</span>, [`ElementCSSInlineStyle`](https://developer.mozilla.org/en-US/docs/Web/API/ElementCSSInlineStyle), [`GlobalEventHandlers`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers), [`HTMLOrForeignElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOrForeignElement) and <span class="page-not-created">`TouchEventHandlers`</span>.*

<span class="page-not-created">`HTMLElement.attachInternals()`</span>   
Attaches an <span class="page-not-created">`ElementInternals`</span> instance to the custom element.

[`HTMLOrForeignElement.blur()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOrForeignElement/blur)  
Removes keyboard focus from the currently focused element.

[`HTMLElement.click()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/click)  
Sends a mouse click event to the element.

[`HTMLOrForeignElement.focus()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOrForeignElement/focus)  
Makes the element the current keyboard focus.

[Events](#events "Permalink to Events")
---------------------------------------

Listen to these events using `addEventListener()` or by assigning an event listener to the `oneventname` property of this interface.

[`invalid`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/invalid_event "invalid")  
Fired when an element does not satisfy its constraints during constraint validation.  
Also available via the [`oninvalid`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oninvalid "oninvalid") property.

### [Animation events](#animation_events "Permalink to Animation events")

[`animationcancel`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/animationcancel_event "animationcancel")  
Fired when an animation unexpectedly aborts.  
Also available via the [`onanimationcancel`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onanimationcancel "onanimationcancel") property.

[`animationend`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/animationend_event "animationend")  
Fired when an animation has completed normally.  
Also available via the [`onanimationend`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onanimationend "onanimationend") property.

[`animationiteration`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/animationiteration_event "animationiteration")  
Fired when an animation iteration has completed.  
Also available via the [`onanimationiteration`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onanimationiteration "onanimationiteration") property.

[`animationstart`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/animationstart_event "animationstart")  
Fired when an animation starts.  
Also available via the [`onanimationstart`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onanimationstart "onanimationstart") property.

### [Input events](#input_events "Permalink to Input events")

[`beforeinput`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/beforeinput_event "beforeinput")  
Fired when the value of an [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input), [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select), or [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea) element is about to be modified.

[`input`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/input_event "input")  
Fired when the `value` of an [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input), [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select), or [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea) element has been changed.  
Also available via the [`oninput`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oninput "oninput") property.

[`change`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/change_event "change")  
Fired when the `value` of an [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input), [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select), or [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea) element has been changed and committed by the user. Unlike the [`input`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/input_event "input") event, the `change` event is not necessarily fired for each alteration to an element's `value`.

### [Pointer events](#pointer_events "Permalink to Pointer events")

[`gotpointercapture`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/gotpointercapture_event "gotpointercapture")  
Fired when an element captures a pointer using [`setPointerCapture()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/setPointerCapture "setPointerCapture()").  
Also available via the [`ongotpointercapture`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ongotpointercapture "ongotpointercapture") property.

[`lostpointercapture`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/lostpointercapture_event "lostpointercapture")  
Fired when a [captured pointer](https://developer.mozilla.org/en-US/docs/Web/API/Pointer_events#pointer_capture) is released.  
Also available via the [`onlostpointercapture`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onlostpointercapture "onlostpointercapture") property.

[`pointercancel`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/pointercancel_event "pointercancel")  
Fired when a pointer event is canceled.  
Also available via the [`onpointercancel`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointercancel "onpointercancel") property.

[`pointerdown`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/pointerdown_event "pointerdown")  
Fired when a pointer becomes active.  
Also available via the [`onpointerdown`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointerdown "onpointerdown") property.

[`pointerenter`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/pointerenter_event "pointerenter")  
Fired when a pointer is moved into the hit test boundaries of an element or one of its descendants.  
Also available via the [`onpointerenter`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointerenter "onpointerenter") property.

[`pointerleave`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/pointerleave_event "pointerleave")  
Fired when a pointer is moved out of the hit test boundaries of an element.  
Also available via the [`onpointerleave`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointerleave "onpointerleave") property.

[`pointermove`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/pointermove_event "pointermove")  
Fired when a pointer changes coordinates.  
Also available via the [`onpointermove`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointermove "onpointermove") property.

[`pointerout`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/pointerout_event "pointerout")  
Fired when a pointer is moved out of the *hit test* boundaries of an element (among other reasons).  
Also available via the [`onpointerout`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointerout "onpointerout") property.

[`pointerover`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/pointerover_event "pointerover")  
Fired when a pointer is moved into an element's hit test boundaries.  
Also available via the [`onpointerover`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointerover "onpointerover") property.

[`pointerup`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/pointerup_event "pointerup")  
Fired when a pointer is no longer active.  
Also available via the [`onpointerup`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointerup "onpointerup") property.

### [Transition events](#transition_events "Permalink to Transition events")

[`transitioncancel`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/transitioncancel_event "transitioncancel")  
Fired when a [CSS transition](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions) is canceled.  
Also available via the [`ontransitioncancel`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ontransitioncancel "ontransitioncancel") property.

[`transitionend`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/transitionend_event "transitionend")  
Fired when a [CSS transition](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions) has completed.  
Also available via the [`ontransitionend`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ontransitionend "ontransitionend") property.

[`transitionrun`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/transitionrun_event "transitionrun")  
Fired when a [CSS transition](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions) is first created.  
Also available via the <span class="page-not-created">`ontransitionrun`</span> property.

[`transitionstart`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/transitionstart_event "transitionstart")  
Fired when a [CSS transition](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions) has actually started.  
Also available via the <span class="page-not-created">`ontransitionstart`</span> property.

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#extensions-to-the-htmlelement-interface" class="external">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'HTMLElement' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Added the following properties: <code>offsetParent</code>, <code>offsetTop</code>, <code>offsetLeft</code>, <code>offsetWidth</code>, and <code>offsetHeight</code>.</td></tr><tr class="even"><td><a href="https://html.spec.whatwg.org/multipage/elements.html#htmlelement" class="external">HTML Living Standard<br />
<span class="small">The definition of 'HTMLElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Added the following properties: <code>translate</code>, <code>itemScope</code>, <code>itemType</code>, <code>itemId</code>, <code>itemRef</code>, <code>itemProp</code>, <code>properties</code>, and <code>itemValue</code>.<br />
Added the following method: <code>forceSpellcheck()</code>.<br />
Moved the <code>onXYZ</code> attributes to the <a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers"><code>GlobalEventHandlers</code></a> interface and added an inheritance from it.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/dom.html#htmlelement" class="external">HTML5<br />
<span class="small">The definition of 'HTMLElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Added the following properties: <code>dataset</code>, <code>hidden</code>, <code>tabIndex</code>, <code>accessKey</code>, <code>accessKeyLabel</code>, <code>draggable</code>, <code>dropzone</code>, <code>contentEditable</code>, <code>isContentEditable</code>, <code>contextMenu</code>, <code>spellcheck</code>, <code>commandType</code>, <code>commandLabel</code>, <code>commandIcon</code>, <code>commandHidden</code>, <code>commandDisabled</code>, <code>commandChecked</code>, <code>style</code>, and all the <code>onXYZ</code> properties.<br />
Moved the <code>id</code> and <code>className</code> properties to the <a href="https://developer.mozilla.org/en-US/docs/Web/API/Element"><code>Element</code></a> interface.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-011100101" class="external">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'HTMLElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/DOM-Level-2-HTML/" class="external" title="The &#39;Document Object Model (DOM) Level 2 HTML Specification&#39; specification">Document Object Model (DOM) Level 2 HTML Specification</a></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-html.html#ID-011100101" class="external">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'HTMLElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [`Element`](https://developer.mozilla.org/en-US/docs/Web/API/Element)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/htmlelement/index.html "Folder: en-us/web/api/htmlelement (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FHTMLElement%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fhtmlelement%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FHTMLElement%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fhtmlelement%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fcb20a8045f6cbdbd224b1068e46c8644470dd8c3%0A*+Document+last+modified%3A+2021-06-01T09%3A10%3A31.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22HTMLElement%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Jun 1, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/contributors.txt)

Change your languageSelect your preferred language English (US)EspañolFrançais日本語한국어PolskiPortuguês (do Brasil)Русский中文 (简体)正體中文 (繁體)

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
    8.  [`input`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/input_event)
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
6.  Related pages for HTML DOM
    1.  [`BeforeUnloadEvent`](https://developer.mozilla.org/en-US/docs/Web/API/BeforeUnloadEvent)
    2.  [`DOMStringMap`](https://developer.mozilla.org/en-US/docs/Web/API/DOMStringMap)
    3.  [`ErrorEvent`](https://developer.mozilla.org/en-US/docs/Web/API/ErrorEvent)
    4.  [`GlobalEventHandlers`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers)
    5.  [`HTMLAnchorElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAnchorElement)
    6.  [`HTMLAreaElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement)
    7.  [`HTMLAudioElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAudioElement)
    8.  [`HTMLBRElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLBRElement)
    9.  [`HTMLBaseElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLBaseElement)
    10. [`HTMLBaseFontElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLBaseFontElement)
    11. [`HTMLBodyElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLBodyElement)
    12. [`HTMLButtonElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLButtonElement)
    13. [`HTMLCanvasElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement)
    14. [`HTMLContentElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLContentElement)
    15. [`HTMLDListElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDListElement)
    16. [`HTMLDataElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDataElement)
    17. [`HTMLDataListElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDataListElement)
    18. [`HTMLDialogElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDialogElement)
    19. [`HTMLDivElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDivElement)
    20. [`HTMLDocument`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDocument)
    21. [`HTMLEmbedElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLEmbedElement)
    22. [`HTMLFieldSetElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFieldSetElement)
    23. [`HTMLFormControlsCollection`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormControlsCollection)
    24. [`HTMLFormElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement)
    25. [`HTMLFrameSetElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFrameSetElement)
    26. [`HTMLHRElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLHRElement)
    27. [`HTMLHeadElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLHeadElement)
    28. [`HTMLHeadingElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLHeadingElement)
    29. [`HTMLHtmlElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLHtmlElement)
    30. [`HTMLIFrameElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLIFrameElement)
    31. [`HTMLImageElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement)
    32. [`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement)
    33. [`HTMLIsIndexElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLIsIndexElement)
    34. [`HTMLKeygenElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLKeygenElement)
    35. [`HTMLLIElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLLIElement)
    36. [`HTMLLabelElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLLabelElement)
    37. [`HTMLLegendElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLLegendElement)
    38. [`HTMLLinkElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLLinkElement)
    39. [`HTMLMapElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMapElement)
    40. [`HTMLMediaElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement)
    41. [`HTMLMetaElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMetaElement)
    42. [`HTMLMeterElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMeterElement)
    43. [`HTMLModElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLModElement)
    44. [`HTMLOListElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOListElement)
    45. [`HTMLObjectElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLObjectElement)
    46. [`HTMLOptGroupElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOptGroupElement)
    47. [`HTMLOptionElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOptionElement)
    48. [`HTMLOptionsCollection`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOptionsCollection)
    49. [`HTMLOutputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOutputElement)
    50. [`HTMLParagraphElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLParagraphElement)
    51. [`HTMLParamElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLParamElement)
    52. [`HTMLPictureElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLPictureElement)
    53. [`HTMLPreElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLPreElement)
    54. [`HTMLProgressElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLProgressElement)
    55. [`HTMLQuoteElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLQuoteElement)
    56. [`HTMLScriptElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLScriptElement)
    57. [`HTMLSelectElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement)
    58. [`HTMLShadowElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLShadowElement)
    59. [`HTMLSourceElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSourceElement)
    60. [`HTMLSpanElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSpanElement)
    61. [`HTMLStyleElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLStyleElement)
    62. [`HTMLTableCaptionElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableCaptionElement)
    63. [`HTMLTableCellElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableCellElement)
    64. [`HTMLTableColElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableColElement)
    65. [`HTMLTableDataCellElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableDataCellElement)
    66. [`HTMLTableElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableElement)
    67. [`HTMLTableHeaderCellElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableHeaderCellElement)
    68. [`HTMLTableRowElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableRowElement)
    69. [`HTMLTableSectionElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableSectionElement)
    70. [`HTMLTemplateElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTemplateElement)
    71. [`HTMLTextAreaElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTextAreaElement)
    72. [`HTMLTimeElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTimeElement)
    73. [`HTMLTitleElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTitleElement)
    74. [`HTMLTrackElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTrackElement)
    75. [`HTMLUListElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLUListElement)
    76. [`HTMLUnknownElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLUnknownElement)
    77. [`HTMLVideoElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLVideoElement)
    78. [`HashChangeEvent`](https://developer.mozilla.org/en-US/docs/Web/API/HashChangeEvent)
    79. [`History`](https://developer.mozilla.org/en-US/docs/Web/API/History)
    80. [`ImageData`](https://developer.mozilla.org/en-US/docs/Web/API/ImageData)
    81. [`Location`](https://developer.mozilla.org/en-US/docs/Web/API/Location)
    82. [`MessageChannel`](https://developer.mozilla.org/en-US/docs/Web/API/MessageChannel)
    83. [`MessageEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MessageEvent)
    84. [`MessagePort`](https://developer.mozilla.org/en-US/docs/Web/API/MessagePort)
    85. [`Navigator`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator)
    86. [`NavigatorGeolocation`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorGeolocation)
    87. [`NavigatorID`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorID)
    88. [`NavigatorLanguage`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorLanguage)
    89. [`NavigatorOnLine`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorOnLine)
    90. [`NavigatorPlugins`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorPlugins)
    91. [`PageTransitionEvent`](https://developer.mozilla.org/en-US/docs/Web/API/PageTransitionEvent)
    92. [`Plugin`](https://developer.mozilla.org/en-US/docs/Web/API/Plugin)
    93. [`PluginArray`](https://developer.mozilla.org/en-US/docs/Web/API/PluginArray)
    94. [`PopStateEvent`](https://developer.mozilla.org/en-US/docs/Web/API/PopStateEvent)
    95. [`PortCollection`](https://developer.mozilla.org/en-US/docs/Web/API/PortCollection)
    96. [`PromiseRejectionEvent`](https://developer.mozilla.org/en-US/docs/Web/API/PromiseRejectionEvent)
    97. [`RadioNodeList`](https://developer.mozilla.org/en-US/docs/Web/API/RadioNodeList)
    98. [`Transferable`](https://developer.mozilla.org/en-US/docs/Web/API/Transferable)
    99. [`ValidityState`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState)
    100. [`Window`](https://developer.mozilla.org/en-US/docs/Web/API/Window)
    101. [`WindowBase64`](https://developer.mozilla.org/en-US/docs/Web/API/WindowBase64)
    102. [`WindowEventHandlers`](https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers)
    103. [`WindowTimers`](https://developer.mozilla.org/en-US/docs/Web/API/WindowTimers)

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
