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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement" class="breadcrumb-current-page"><span data-property="name">HTMLSelectElement</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Properties](#properties)
-   [Methods](#methods)
-   [Events](#events)
-   [Example](#example)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

HTMLSelectElement
=================

The `HTMLSelectElement` interface represents a [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select) HTML Element. These elements also share all of the properties and methods of other HTML elements via the [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement) interface.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

*This interface inherits the properties of [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement), and of [`Element`](https://developer.mozilla.org/en-US/docs/Web/API/Element) and [`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node).*

[`HTMLSelectElement.autofocus`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/autofocus)  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) reflecting the [`autofocus`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select#attr-autofocus) HTML attribute, which indicates whether the control should have input focus when the page loads, unless the user overrides it, for example by typing in a different control. Only one form-associated element in a document can have this attribute specified.

[`HTMLSelectElement.disabled`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/disabled)  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) reflecting the [`disabled`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select#attr-disabled) HTML attribute, which indicates whether the control is disabled. If it is disabled, it does not accept clicks.

[`HTMLSelectElement.form`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/form)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
An [`HTMLFormElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement) referencing the form that this element is associated with. If the element is not associated with of a [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form) element, then it returns `null`.

[`HTMLSelectElement.labels`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/labels)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
A [`NodeList`](https://developer.mozilla.org/en-US/docs/Web/API/NodeList) of [`<label>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label) elements associated with the element.

<span class="page-not-created">`HTMLSelectElement.length`</span>  
An `unsigned long` The number of [`<option>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/option) elements in this `select` element.

<span class="page-not-created">`HTMLSelectElement.multiple`</span>  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) reflecting the [`multiple`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select#attr-multiple) HTML attribute, which indicates whether multiple items can be selected.

<span class="page-not-created">`HTMLSelectElement.name`</span>  
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the [`name`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select#attr-name) HTML attribute, containing the name of this control used by servers and DOM search functions.

[`HTMLSelectElement.options`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/options)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
An [`HTMLOptionsCollection`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOptionsCollection) representing the set of [`<option>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/option) ([`HTMLOptionElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOptionElement)) elements contained by this element.

<span class="page-not-created">`HTMLSelectElement.required`</span>  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) reflecting the [`required`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select#attr-required) HTML attribute, which indicates whether the user is required to select a value before submitting the form.

[`HTMLSelectElement.selectedIndex`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/selectedIndex)  
A `long` reflecting the index of the first selected [`<option>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/option) element. The value `-1` indicates no element is selected.

[`HTMLSelectElement.selectedOptions`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/selectedOptions)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
An [`HTMLCollection`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCollection) representing the set of [`<option>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/option) elements that are selected.

<span class="page-not-created">`HTMLSelectElement.size`</span>  
A `long` reflecting the [`size`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select#attr-size) HTML attribute, which contains the number of visible items in the control. The default is 1, unless `multiple` is `true`, in which case it is 4.

[`HTMLSelectElement.type`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/type)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) represeting the form control's type. When `multiple` is `true`, it returns `"select-multiple"`; otherwise, it returns `"select-one"`.

<span class="page-not-created">`HTMLSelectElement.validationMessage`</span><span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) representing a localized message that describes the validation constraints that the control does not satisfy (if any). This attribute is the empty string if the control is not a candidate for constraint validation (`willValidate` is false), or it satisfies its constraints.

<span class="page-not-created">`HTMLSelectElement.validity`</span><span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
A [`ValidityState`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState) reflecting the validity state that this control is in.

<span class="page-not-created">`HTMLSelectElement.value`</span>  
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the value of the form control. Returns the `value` property of the first selected option element if there is one, otherwise the empty string.

<span class="page-not-created">`HTMLSelectElement.willValidate`</span><span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that indicates whether the button is a candidate for constraint validation. It is `false` if any conditions bar it from constraint validation.

[Methods](#methods "Permalink to Methods")
------------------------------------------

*This interface inherits the methods of [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement), and of [`Element`](https://developer.mozilla.org/en-US/docs/Web/API/Element) and [`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node).*

[`HTMLSelectElement.add()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/add)  
Adds an element to the collection of `option` elements for this `select` element.

<span class="page-not-created">`HTMLSelectElement.blur()`</span>   
Removes input focus from this element. *This method is now implemented on [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)*.

[`HTMLSelectElement.checkValidity()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/checkValidity)  
Checks whether the element has any constraints and whether it satisfies them. If the element fails its constraints, the browser fires a cancelable [`invalid`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/invalid_event "invalid") event at the element (and returns `false`).

<span class="page-not-created">`HTMLSelectElement.focus()`</span>   
Gives input focus to this element. *This method is now implemented on [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)*.

[`HTMLSelectElement.item()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/item)  
Gets an item from the options collection for this [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select) element. You can also access an item by specifying the index in array-style brackets or parentheses, without calling this method explicitly.

[`HTMLSelectElement.namedItem()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/namedItem)  
Gets the item in the options collection with the specified name. The name string can match either the `id` or the `name` attribute of an option node. You can also access an item by specifying the name in array-style brackets or parentheses, without calling this method explicitly.

[`HTMLSelectElement.remove()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/remove)  
Removes the element at the specified index from the options collection for this `select` element.

<span class="page-not-created">`HTMLSelectElement.reportValidity()`</span>  
This method reports the problems with the constraints on the element, if any, to the user. If there are problems, it fires a cancelable [`invalid`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/invalid_event "invalid") event at the element, and returns `false`; if there are no problems, it returns `true`.

[`HTMLSelectElement.setCustomValidity()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/setCustomValidity)  
Sets the custom validity message for the selection element to the specified message. Use the empty string to indicate that the element does *not* have a custom validity error.

[Events](#events "Permalink to Events")
---------------------------------------

Listen to these events using [`addEventListener()`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener "addEventListener()") or by assigning an event listener to the `oneventname` property of this interface:

[`input`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/input_event "input") event  
Fires when the `value` of an [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input), [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select), or [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea) element has been changed.

[Example](#example "Permalink to Example")
------------------------------------------

### [Get information about the selected option](#get_information_about_the_selected_option "Permalink to Get information about the selected option")

    /* assuming we have the following HTML
    <select id='s'>
        <option>First</option>
        <option selected>Second</option>
        <option>Third</option>
    </select>
    */

    var select = document.getElementById('s');

    // return the index of the selected option
    console.log(select.selectedIndex); // 1

    // return the value of the selected option
    console.log(select.options[select.selectedIndex].value) // Second

A better way to track changes to the user's selection is to watch for the [`change`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/change_event "change") event to occur on the `<select>`. This will tell you when the value changes, and you can then update anything you need to. See [the example provided](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/change_event#select_element) in the documentation for the `change` event for details.

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#htmlselectelement" class="external">HTML Living Standard<br />
<span class="small">The definition of 'HTMLSelectElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Since the latest snapshot, <a href="https://www.w3.org/TR/html52/" class="external" title="The &#39;HTML5&#39; specification">HTML5</a>, it adds the <code>autocomplete</code> property and the <code>reportValidity()</code> method.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/forms.html#htmlselectelement" class="external">HTML5<br />
<span class="small">The definition of 'HTMLSelectElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Is a snapshot of <a href="https://html.spec.whatwg.org/multipage/" class="external" title="The &#39;HTML Living Standard&#39; specification">HTML Living Standard</a>.<br />
It adds the <code>autofocus</code>, <code>form</code>, <code>required</code>, <code>labels</code>, <code>selectedOptions</code>, <code>willValidate</code>, <code>validity</code> and <code>validationMessage</code> properties.<br />
The <code>tabindex</code> property and the <code>blur()</code> and <code>focus()</code> methods have been moved to <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement"><code>HTMLElement</code></a>.<br />
The methods <code>item()</code>, <code>namedItem()</code>, <code>checkValidity()</code> and <code>setCustomValidity()</code>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-94282980" class="external">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'HTMLSelectElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td><code>options</code> now returns an <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLOptionsCollection"><code>HTMLOptionsCollection</code></a>.<br />
<code>length</code> now returns an <code>unsigned long</code>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-html.html#ID-94282980" class="external">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'HTMLSelectElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   The [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select) HTML element, which implements this interface.

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/htmlselectelement/index.html "Folder: en-us/web/api/htmlselectelement (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FHTMLSelectElement%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fhtmlselectelement%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FHTMLSelectElement%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fhtmlselectelement%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fcb20a8045f6cbdbd224b1068e46c8644470dd8c3%0A*+Document+last+modified%3A+2021-06-01T09%3A10%3A31.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22HTMLSelectElement%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Jun 1, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/contributors.txt)

Change your languageSelect your preferred language English (US)EspañolFrançais日本語한국어PolskiPortuguês (do Brasil)Русский中文 (简体)正體中文 (繁體)

Change language

#### Related Topics

1.  **[`HTMLSelectElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement)**
2.  Properties
    1.  [`autofocus`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/autofocus)
    2.  [`disabled`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/disabled)
    3.  [`form`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/form)
    4.  [`labels`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/labels)
    5.  [`options`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/options)
    6.  [`selectedIndex`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/selectedIndex)
    7.  [`selectedOptions`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/selectedOptions)
    8.  [`type`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/type)
3.  Methods
    1.  [`add()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/add)
    2.  [`checkValidity()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/checkValidity)
    3.  [`item()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/item)
    4.  [`namedItem()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/namedItem)
    5.  [`remove()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/remove)
    6.  [`setCustomValidity()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/setCustomValidity)
4.  Inheritance:
    1.  [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
    2.  [`Element`](https://developer.mozilla.org/en-US/docs/Web/API/Element)
    3.  [`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node)
    4.  [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)
5.  Related pages for HTML DOM
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
    21. [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
    22. [`HTMLEmbedElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLEmbedElement)
    23. [`HTMLFieldSetElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFieldSetElement)
    24. [`HTMLFormControlsCollection`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormControlsCollection)
    25. [`HTMLFormElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement)
    26. [`HTMLFrameSetElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFrameSetElement)
    27. [`HTMLHRElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLHRElement)
    28. [`HTMLHeadElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLHeadElement)
    29. [`HTMLHeadingElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLHeadingElement)
    30. [`HTMLHtmlElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLHtmlElement)
    31. [`HTMLIFrameElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLIFrameElement)
    32. [`HTMLImageElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement)
    33. [`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement)
    34. [`HTMLIsIndexElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLIsIndexElement)
    35. [`HTMLKeygenElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLKeygenElement)
    36. [`HTMLLIElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLLIElement)
    37. [`HTMLLabelElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLLabelElement)
    38. [`HTMLLegendElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLLegendElement)
    39. [`HTMLLinkElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLLinkElement)
    40. [`HTMLMapElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMapElement)
    41. [`HTMLMediaElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement)
    42. [`HTMLMetaElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMetaElement)
    43. [`HTMLMeterElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMeterElement)
    44. [`HTMLModElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLModElement)
    45. [`HTMLOListElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOListElement)
    46. [`HTMLObjectElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLObjectElement)
    47. [`HTMLOptGroupElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOptGroupElement)
    48. [`HTMLOptionElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOptionElement)
    49. [`HTMLOptionsCollection`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOptionsCollection)
    50. [`HTMLOutputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOutputElement)
    51. [`HTMLParagraphElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLParagraphElement)
    52. [`HTMLParamElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLParamElement)
    53. [`HTMLPictureElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLPictureElement)
    54. [`HTMLPreElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLPreElement)
    55. [`HTMLProgressElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLProgressElement)
    56. [`HTMLQuoteElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLQuoteElement)
    57. [`HTMLScriptElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLScriptElement)
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
