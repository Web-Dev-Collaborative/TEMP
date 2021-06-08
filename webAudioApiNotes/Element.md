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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/Element" class="breadcrumb-current-page"><span data-property="name">Element</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Properties](#properties)
-   [Methods](#methods)
-   [Events](#events)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)

Element
=======

<span class="seoSummary">**`Element`** is the most general base class from which all element objects (i.e. objects that represent elements) in a [`Document`](https://developer.mozilla.org/en-US/docs/Web/API/Document) inherit. It only has methods and properties common to all kinds of elements. More specific classes inherit from `Element`.</span> For example, the [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement) interface is the base interface for HTML elements, while the [`SVGElement`](https://developer.mozilla.org/en-US/docs/Web/API/SVGElement) interface is the basis for all SVG elements. Most functionality is specified further down the class hierarchy.

Languages outside the realm of the Web platform, like XUL through the `XULElement` interface, also implement `Element`.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

*`Element` inherits properties from its parent interface, [`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node), and by extension that interface's parent, [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget).*

[`Element.assignedSlot`](https://developer.mozilla.org/en-US/docs/Web/API/Element/assignedSlot)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`HTMLSlotElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSlotElement) representing the [`<slot>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/slot) the node is inserted in.

[`Element.attributes`](https://developer.mozilla.org/en-US/docs/Web/API/Element/attributes) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`NamedNodeMap`](https://developer.mozilla.org/en-US/docs/Web/API/NamedNodeMap) object containing the assigned attributes of the corresponding HTML element.

[`Element.childElementCount`](https://developer.mozilla.org/en-US/docs/Web/API/Element/childElementCount) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the number of child elements of this element.

[`Element.children`](https://developer.mozilla.org/en-US/docs/Web/API/Element/children) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the child elements of this element.

[`Element.classList`](https://developer.mozilla.org/en-US/docs/Web/API/Element/classList) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`DOMTokenList`](https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList) containing the list of class attributes.

[`Element.className`](https://developer.mozilla.org/en-US/docs/Web/API/Element/className)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) representing the class of the element.

[`Element.clientHeight`](https://developer.mozilla.org/en-US/docs/Web/API/Element/clientHeight) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) representing the inner height of the element.

[`Element.clientLeft`](https://developer.mozilla.org/en-US/docs/Web/API/Element/clientLeft) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) representing the width of the left border of the element.

[`Element.clientTop`](https://developer.mozilla.org/en-US/docs/Web/API/Element/clientTop) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) representing the width of the top border of the element.

[`Element.clientWidth`](https://developer.mozilla.org/en-US/docs/Web/API/Element/clientWidth) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) representing the inner width of the element.

[`Element.firstElementChild`](https://developer.mozilla.org/en-US/docs/Web/API/Element/firstElementChild) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the first child element of this element.

[`Element.id`](https://developer.mozilla.org/en-US/docs/Web/API/Element/id)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) representing the id of the element.

[`Element.innerHTML`](https://developer.mozilla.org/en-US/docs/Web/API/Element/innerHTML)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) representing the markup of the element's content.

[`Element.lastElementChild`](https://developer.mozilla.org/en-US/docs/Web/API/Element/lastElementChild) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the last child element of this element.

[`Element.localName`](https://developer.mozilla.org/en-US/docs/Web/API/Element/localName) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) representing the local part of the qualified name of the element.

[`Element.namespaceURI`](https://developer.mozilla.org/en-US/docs/Web/API/Element/namespaceURI) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
The namespace URI of the element, or `null` if it is no namespace.

**Note:** In Firefox 3.5 and earlier, HTML elements are in no namespace. In later versions, HTML elements are in the `http://www.w3.org/1999/xhtml` namespace in both HTML and XML trees.

[`Element.nextElementSibling`](https://developer.mozilla.org/en-US/docs/Web/API/Element/nextElementSibling) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Is an [`Element`](https://developer.mozilla.org/en-US/docs/Web/API/Element), the element immediately following the given one in the tree, or `null` if there's no sibling node.

[`Element.outerHTML`](https://developer.mozilla.org/en-US/docs/Web/API/Element/outerHTML)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) representing the markup of the element including its content. When used as a setter, replaces the element with nodes parsed from the given string.

[`Element.part`](https://developer.mozilla.org/en-US/docs/Web/API/Element/part)  
Represents the part identifier(s) of the element (i.e. set using the `part` attribute), returned as a [`DOMTokenList`](https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList).

[`Element.prefix`](https://developer.mozilla.org/en-US/docs/Web/API/Element/prefix) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) representing the namespace prefix of the element, or `null` if no prefix is specified.

[`Element.previousElementSibling`](https://developer.mozilla.org/en-US/docs/Web/API/Element/previousElementSibling) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Is a [`Element`](https://developer.mozilla.org/en-US/docs/Web/API/Element), the element immediately preceding the given one in the tree, or `null` if there is no sibling element.

[`Element.scrollHeight`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollHeight) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) representing the scroll view height of an element.

[`Element.scrollLeft`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollLeft)  
Is a [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) representing the left scroll offset of the element.

[`Element.scrollLeftMax`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollLeftMax) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) representing the maximum left scroll offset possible for the element.

[`Element.scrollTop`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollTop)  
A [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) representing number of pixels the top of the document is scrolled vertically.

[`Element.scrollTopMax`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollTopMax) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) representing the maximum top scroll offset possible for the element.

[`Element.scrollWidth`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollWidth) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) representing the scroll view width of the element.

[`Element.shadowRoot`](https://developer.mozilla.org/en-US/docs/Web/API/Element/shadowRoot)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the open shadow root that is hosted by the element, or null if no open shadow root is present.

[`Element.openOrClosedShadowRoot`](https://developer.mozilla.org/en-US/docs/Web/API/Element/openOrClosedShadowRoot) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the shadow root that is hosted by the element, regardless if its open or closed. **Available only to [WebExtensions](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions).**

[`Element.slot`](https://developer.mozilla.org/en-US/docs/Web/API/Element/slot)   
Returns the name of the shadow DOM slot the element is inserted in.

[`Element.tagName`](https://developer.mozilla.org/en-US/docs/Web/API/Element/tagName) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) with the name of the tag for the given element.

### [Properties included from ARIA](#properties_included_from_aria "Permalink to Properties included from ARIA")

*The `Element` interface includes the following properties, defined on the `ARIAMixin` mixin.*

[`Element.ariaAtomic`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaAtomic)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the `aria-atomic` attribute, which indicates whether assistive technologies will present all, or only parts of, the changed region based on the change notifications defined by the `aria-relevant` attribute.

[`Element.ariaAutoComplete`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaAutoComplete)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the `aria-autocomplete` attribute, which indicates whether inputting text could trigger display of one or more predictions of the user's intended value for a combobox, searchbox, or textbox and specifies how predictions would be presented if they were made.

[`Element.ariaBusy`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaBusy)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the `aria-busy` attribute, which indicates whether an element is being modified, as assistive technologies may want to wait until the modifications are complete before exposing them to the user.

[`Element.ariaChecked`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaChecked)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the `aria-checked` attribute, which indicates the current "checked" state of checkboxes, radio buttons, and other widgets that have a checked state.

[`Element.ariaColCount`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaColCount)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the `aria-colcount` attribute, which defines the number of columns in a table, grid, or treegrid.

[`Element.ariaColIndex`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaColIndex)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the `aria-colindex` attribute, which defines an element's column index or position with respect to the total number of columns within a table, grid, or treegrid.

[`Element.ariaColIndexText`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaColIndexText)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the `aria-colindextext` attribute, which defines a human readable text alternative of aria-colindex.

[`Element.ariaColSpan`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaColSpan)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the `aria-colspan` attribute, which defines the number of columns spanned by a cell or gridcell within a table, grid, or treegrid.

[`Element.ariaCurrent`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaCurrent)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the `aria-current` attribute, which indicates the element that represents the current item within a container or set of related elements.

[`Element.ariaDescription`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaDescription)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the `aria-description` attribute, which defines a string value that describes or annotates the current element.

[`Element.ariaDisabled`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaDisabled)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the `aria-disabled` attribute, which indicates that the element is perceivable but disabled, so it is not editable or otherwise operable.

[`Element.ariaExpanded`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaExpanded)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the `aria-expanded` attribute, which indicates whether a grouping element owned or controlled by this element is expanded or collapsed.

[`Element.ariaHasPopup`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaHasPopup)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the `aria-haspopup` attribute, which indicates the availability and type of interactive popup element, such as menu or dialog, that can be triggered by an element.

[`Element.ariaHidden`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaHidden)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the `aria-hidden` attribute, which indicates whether the element is exposed to an accessibility API.

[`Element.ariaKeyShortcuts`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaKeyShortcuts)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the `aria-keyshortcuts` attribute, which indicates keyboard shortcuts that an author has implemented to activate or give focus to an element.

[`Element.ariaLabel`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaLabel)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the `aria-label` attribute, which defines a string value that labels the current element.

[`Element.ariaLevel`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaLevel)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the `aria-level` attribute, which defines the hierarchical level of an element within a structure.

[`Element.ariaLive`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaLive)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the `aria-live` attribute, which indicates that an element will be updated, and describes the types of updates the user agents, assistive technologies, and user can expect from the live region.

[`Element.ariaModal`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaModal)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the `aria-modal` attribute, which indicates whether an element is modal when displayed.

[`Element.ariaMultiline`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaMultiline)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the `aria-multiline` attribute, which indicates whether a text box accepts multiple lines of input or only a single line.

[`Element.ariaMultiSelectable`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaMultiSelectable)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the `aria-multiselectable` attribute, which indicates that the user may select more than one item from the current selectable descendants.

[`Element.ariaOrientation`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaOrientation)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the `aria-orientation` attribute, which indicates whether the element's orientation is horizontal, vertical, or unknown/ambiguous.

[`Element.ariaPlaceholder`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaPlaceholder)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the `aria-placeholder` attribute, which defines a short hint intended to aid the user with data entry when the control has no value.

[`Element.ariaPosInSet`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaPosInSet)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the `aria-posinset` attribute, which defines an element's number or position in the current set of listitems or treeitems.

[`Element.ariaPressed`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaPressed)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the `aria-pressed` attribute, which indicates the current "pressed" state of toggle buttons.

[`Element.ariaReadOnly`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaReadOnly)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the `aria-readonly` attribute, which indicates that the element is not editable, but is otherwise operable.

[`Element.ariaRelevant`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaRelevant)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the `aria-relevant` attribute, which indicates what notifications the user agent will trigger when the accessibility tree within a live region is modified. This is used to describe what changes in an `aria-live` region are relevant and should be announced.

[`Element.ariaRequired`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaRequired)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the `aria-required` attribute, which indicates that user input is required on the element before a form may be submitted.

[`Element.ariaRoleDescription`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaRoleDescription)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the `aria-roledescription` attribute, which defines a human-readable, author-localized description for the role of an element.

[`Element.ariaRowCount`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaRowCount)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the `aria-rowcount` attribute, which defines the total number of rows in a table, grid, or treegrid.

[`Element.ariaRowIndex`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaRowIndex)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the `aria-rowindex` attribute, which defines an element's row index or position with respect to the total number of rows within a table, grid, or treegrid.

[`Element.ariaRowIndexText`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaRowIndexText)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the `aria-rowindextext` attribute, which defines a human readable text alternative of aria-rowindex.

[`Element.ariaRowSpan`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaRowSpan)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the `aria-rowspan` attribute, which defines the number of rows spanned by a cell or gridcell within a table, grid, or treegrid.

[`Element.ariaSelected`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaSelected)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the `aria-selected` attribute, which indicates the current "selected" state of elements that have a selected state.

[`Element.ariaSetSize`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaSetSize)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the `aria-setsize` attribute, which defines the number of items in the current set of listitems or treeitems.

[`Element.ariaSort`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaSort)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the `aria-sort` attribute, which indicates if items in a table or grid are sorted in ascending or descending order.

[`Element.ariaValueMax`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaValueMax)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the `aria-valueMax` attribute, which defines the maximum allowed value for a range widget.

[`Element.ariaValueMin`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaValueMin)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the `aria-valueMin` attribute, which defines the minimum allowed value for a range widget.

[`Element.ariaValueNow`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaValueNow)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the `aria-valueNow` attribute, which defines the current value for a range widget.

[`Element.ariaValueText`](https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaValueText)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the `aria-valuetext` attribute, which defines the human readable text alternative of aria-valuenow for a range widget.

### [Event handlers](#handlers "Permalink to Event handlers")

[`Element.onfullscreenchange`](https://developer.mozilla.org/en-US/docs/Web/API/Element/onfullscreenchange)  
An event handler for the `fullscreenchange` event, which is sent when the element enters or exits full-screen mode. This can be used to watch both for successful expected transitions, but also to watch for unexpected changes, such as when your app is running in the background.

[`Element.onfullscreenerror`](https://developer.mozilla.org/en-US/docs/Web/API/Element/onfullscreenerror)  
An event handler for the `fullscreenerror` event, which is sent when an error occurs while attempting to change into full-screen mode.

[Methods](#methods "Permalink to Methods")
------------------------------------------

*`Element` inherits methods from its parents [`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node), and its own parent, [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget).*

[`EventTarget.addEventListener()`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener)  
Registers an event handler to a specific event type on the element.

[`Element.attachShadow()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/attachShadow)  
Attaches a shadow DOM tree to the specified element and returns a reference to its [`ShadowRoot`](https://developer.mozilla.org/en-US/docs/Web/API/ShadowRoot).

[`Element.animate()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/animate)   
A shortcut method to create and run an animation on an element. Returns the created Animation object instance.

[`Element.append()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/append)  
Inserts a set of [`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node) objects or [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) objects after the last child of the element.

[`Element.closest()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/closest)  
Returns the [`Element`](https://developer.mozilla.org/en-US/docs/Web/API/Element) which is the closest ancestor of the current element (or the current element itself) which matches the selectors given in parameter.

[`Element.createShadowRoot()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/createShadowRoot)   
Creates a [shadow DOM](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_shadow_DOM) on the element, turning it into a shadow host. Returns a [`ShadowRoot`](https://developer.mozilla.org/en-US/docs/Web/API/ShadowRoot).

[`Element.computedStyleMap()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/computedStyleMap)   
Returns a [`StylePropertyMapReadOnly`](https://developer.mozilla.org/en-US/docs/Web/API/StylePropertyMapReadOnly) interface which provides a read-only representation of a CSS declaration block that is an alternative to [`CSSStyleDeclaration`](https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleDeclaration).

[`EventTarget.dispatchEvent()`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/dispatchEvent)  
Dispatches an event to this node in the DOM and returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that indicates whether no handler canceled the event.

[`Element.getAnimations()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/getAnimations)   
Returns an array of Animation objects currently active on the element.

[`Element.getAttribute()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/getAttribute)  
Retrieves the value of the named attribute from the current node and returns it as an [`Object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object).

[`Element.getAttributeNames()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/getAttributeNames)  
Returns an array of attribute names from the current element.

[`Element.getAttributeNode()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/getAttributeNode)  
Retrieves the node representation of the named attribute from the current node and returns it as an [`Attr`](https://developer.mozilla.org/en-US/docs/Web/API/Attr).

[`Element.getAttributeNodeNS()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/getAttributeNodeNS)  
Retrieves the node representation of the attribute with the specified name and namespace, from the current node and returns it as an [`Attr`](https://developer.mozilla.org/en-US/docs/Web/API/Attr).

[`Element.getAttributeNS()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/getAttributeNS)  
Retrieves the value of the attribute with the specified name and namespace, from the current node and returns it as an [`Object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object).

[`Element.getBoundingClientRect()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/getBoundingClientRect)  
Returns the size of an element and its position relative to the viewport.

<span class="page-not-created">`Element.getBoxQuads()`</span>   
Returns a list of [`DOMQuad`](https://developer.mozilla.org/en-US/docs/Web/API/DOMQuad) objects representing the CSS fragments of the node.

[`Element.getClientRects()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/getClientRects)  
Returns a collection of rectangles that indicate the bounding rectangles for each line of text in a client.

[`Element.getElementsByClassName()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/getElementsByClassName)  
Returns a live [`HTMLCollection`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCollection) that contains all descendants of the current element that possess the list of classes given in the parameter.

[`Element.getElementsByTagName()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/getElementsByTagName)  
Returns a live [`HTMLCollection`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCollection) containing all descendant elements, of a particular tag name, from the current element.

[`Element.getElementsByTagNameNS()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/getElementsByTagNameNS)  
Returns a live [`HTMLCollection`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCollection) containing all descendant elements, of a particular tag name and namespace, from the current element.

[`Element.hasAttribute()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/hasAttribute)  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating if the element has the specified attribute or not.

[`Element.hasAttributeNS()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/hasAttributeNS)  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating if the element has the specified attribute, in the specified namespace, or not.

[`Element.hasAttributes()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/hasAttributes)  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating if the element has one or more HTML attributes present.

[`Element.hasPointerCapture()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/hasPointerCapture)  
Indicates whether the element on which it is invoked has pointer capture for the pointer identified by the given pointer ID.

[`Element.insertAdjacentElement()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/insertAdjacentElement)  
Inserts a given element node at a given position relative to the element it is invoked upon.

[`Element.insertAdjacentHTML()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/insertAdjacentHTML)  
Parses the text as HTML or XML and inserts the resulting nodes into the tree in the position given.

[`Element.insertAdjacentText()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/insertAdjacentText)  
Inserts a given text node at a given position relative to the element it is invoked upon.

[`Element.matches()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/matches)  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether or not the element would be selected by the specified selector string.

[`Element.prepend()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/prepend)  
Inserts a set of [`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node) objects or [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) objects before the first child of the element.

[`Element.querySelector()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/querySelector)  
Returns the first [`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node) which matches the specified selector string relative to the element.

[`Element.querySelectorAll()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/querySelectorAll)  
Returns a [`NodeList`](https://developer.mozilla.org/en-US/docs/Web/API/NodeList) of nodes which match the specified selector string relative to the element.

[`Element.releasePointerCapture()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/releasePointerCapture)  
Releases (stops) pointer capture that was previously set for a specific [`pointer event`](https://developer.mozilla.org/en-US/docs/Web/API/PointerEvent "pointer event").

[`Element.remove()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/remove)  
Removes the element from the children list of its parent.

[`Element.removeAttribute()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/removeAttribute)  
Removes the named attribute from the current node.

[`Element.removeAttributeNode()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/removeAttributeNode)  
Removes the node representation of the named attribute from the current node.

[`Element.removeAttributeNS()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/removeAttributeNS)  
Removes the attribute with the specified name and namespace, from the current node.

[`EventTarget.removeEventListener()`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/removeEventListener)  
Removes an event listener from the element.

[`Element.replaceChildren()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/replaceChildren)  
Replaces the existing children of a [`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node) with a specified new set of children.

[`Element.replaceWith()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/replaceWith)  
Replaces the element in the children list of its parent with a set of [`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node) or [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) objects.

[`Element.requestFullscreen()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/requestFullScreen)   
Asynchronously asks the browser to make the element full-screen.

[`Element.requestPointerLock()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/requestPointerLock)   
Allows to asynchronously ask for the pointer to be locked on the given element.

[`Element.scroll()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scroll)  
Scrolls to a particular set of coordinates inside a given element.

[`Element.scrollBy()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollBy)  
Scrolls an element by the given amount.

[`Element.scrollIntoView()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollIntoView)   
Scrolls the page until the element gets into the view.

[`Element.scrollTo()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollTo)  
Scrolls to a particular set of coordinates inside a given element.

[`Element.setAttribute()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/setAttribute)  
Sets the value of a named attribute of the current node.

[`Element.setAttributeNode()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/setAttributeNode)  
Sets the node representation of the named attribute from the current node.

[`Element.setAttributeNodeNS()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/setAttributeNodeNS)  
Sets the node representation of the attribute with the specified name and namespace, from the current node.

[`Element.setAttributeNS()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/setAttributeNS)  
Sets the value of the attribute with the specified name and namespace, from the current node.

[`Element.setCapture()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/setCapture)   
Sets up mouse event capture, redirecting all mouse events to this element.

[`Element.setPointerCapture()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/setPointerCapture)  
Designates a specific element as the capture target of future [pointer events](https://developer.mozilla.org/en-US/docs/Web/API/Pointer_events).

[`Element.toggleAttribute()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/toggleAttribute)  
Toggles a boolean attribute, removing it if it is present and adding it if it is not present, on the specified element.

[Events](#events "Permalink to Events")
---------------------------------------

Listen to these events using `addEventListener()` or by assigning an event listener to the `oneventname` property of this interface.

[`cancel`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDialogElement/cancel_event "cancel")  
Fires on a [`<dialog>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dialog) when the user instructs the browser that they wish to dismiss the current open dialog. For example, the browser might fire this event when the user presses the Esc key or clicks a "Close dialog" button which is part of the browser's UI.  
Also available via the [`oncancel`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oncancel "oncancel") property.

[`error`](https://developer.mozilla.org/en-US/docs/Web/API/Element/error_event "error")  
Fired when a resource failed to load, or can't be used. For example, if a script has an execution error or an image can't be found or is invalid.  
Also available via the [`onerror`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onerror "onerror") property.

[`scroll`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scroll_event "scroll")  
Fired when the document view or an element has been scrolled.  
Also available via the [`onscroll`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onscroll "onscroll") property.

[`select`](https://developer.mozilla.org/en-US/docs/Web/API/Element/select_event "select")  
Fired when some text has been selected.  
Also available via the [`onselect`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onselect "onselect") property.

[`show`](https://developer.mozilla.org/en-US/docs/Web/API/Element/show_event "show")  
Fired when a [`contextmenu`](https://developer.mozilla.org/en-US/docs/Web/API/Element/contextmenu_event "contextmenu") event was fired on/bubbled to an element that has a `contextmenu` attribute.

  
Also available via the <span class="page-not-created">`onshow`</span> property.

[`wheel`](https://developer.mozilla.org/en-US/docs/Web/API/Element/wheel_event "wheel")  
Fired when the user rotates a wheel button on a pointing device (typically a mouse).  
Also available via the [`onwheel`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onwheel "onwheel") property.

### [Clipboard events](#clipboard_events "Permalink to Clipboard events")

[`copy`](https://developer.mozilla.org/en-US/docs/Web/API/Element/copy_event "copy")  
Fired when the user initiates a copy action through the browser's user interface.  
Also available via the [`oncopy`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/oncopy "oncopy") property.

[`cut`](https://developer.mozilla.org/en-US/docs/Web/API/Element/cut_event "cut")  
Fired when the user initiates a cut action through the browser's user interface.  
Also available via the [`oncut`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/oncut "oncut") property.

[`paste`](https://developer.mozilla.org/en-US/docs/Web/API/Element/paste_event "paste")  
Fired when the user initiates a paste action through the browser's user interface.  
Also available via the [`onpaste`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/onpaste "onpaste") property.

### [Composition events](#composition_events "Permalink to Composition events")

[`compositionend`](https://developer.mozilla.org/en-US/docs/Web/API/Element/compositionend_event "compositionend")  
Fired when a text composition system such as an [input method editor](https://developer.mozilla.org/en-US/docs/Glossary/Input_method_editor) completes or cancels the current composition session.

[`compositionstart`](https://developer.mozilla.org/en-US/docs/Web/API/Element/compositionstart_event "compositionstart")  
Fired when a text composition system such as an [input method editor](https://developer.mozilla.org/en-US/docs/Glossary/Input_method_editor) starts a new composition session.

[`compositionupdate`](https://developer.mozilla.org/en-US/docs/Web/API/Element/compositionupdate_event "compositionupdate")  
Fired when a new character is received in the context of a text composition session controlled by a text composition system such as an [input method editor](https://developer.mozilla.org/en-US/docs/Glossary/Input_method_editor).

### [Focus events](#focus_events "Permalink to Focus events")

[`blur`](https://developer.mozilla.org/en-US/docs/Web/API/Element/blur_event "blur")  
Fired when an element has lost focus.  
Also available via the [`onblur`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onblur "onblur") property.

[`focus`](https://developer.mozilla.org/en-US/docs/Web/API/Element/focus_event "focus")  
Fired when an element has gained focus.  
Also available via the [`onfocus`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onfocus "onfocus") property

[`focusin`](https://developer.mozilla.org/en-US/docs/Web/API/Element/focusin_event "focusin")  
Fired when an element is about to gain focus.

[`focusout`](https://developer.mozilla.org/en-US/docs/Web/API/Element/focusout_event "focusout")  
Fired when an element is about to lose focus.

### [Fullscreen events](#fullscreen_events "Permalink to Fullscreen events")

[`fullscreenchange`](https://developer.mozilla.org/en-US/docs/Web/API/Element/fullscreenchange_event "fullscreenchange")  
Sent to an [`Element`](https://developer.mozilla.org/en-US/docs/Web/API/Element) when it transitions into or out of [full-screen](https://developer.mozilla.org/en-US/docs/Web/API/Fullscreen_API/Guide) mode.  
Also available via the [`onfullscreenchange`](https://developer.mozilla.org/en-US/docs/Web/API/Element/onfullscreenchange "onfullscreenchange") property.

[`fullscreenerror`](https://developer.mozilla.org/en-US/docs/Web/API/Element/fullscreenerror_event "fullscreenerror")  
Sent to an `Element` if an error occurs while attempting to switch it into or out of [full-screen](https://developer.mozilla.org/en-US/docs/Web/API/Fullscreen_API/Guide) mode.  
Also available via the [`onfullscreenerror`](https://developer.mozilla.org/en-US/docs/Web/API/Element/onfullscreenerror "onfullscreenerror") property.

### [Keyboard events](#keyboard_events "Permalink to Keyboard events")

`keydown`  
Fired when a key is pressed.  
Also available via the [`onkeydown`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onkeydown "onkeydown") property.

`keypress`  
Fired when a key that produces a character value is pressed down.

  
Also available via the [`onkeypress`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onkeypress "onkeypress") property.

`keyup`  
Fired when a key is released.  
Also available via the [`onkeyup`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onkeyup "onkeyup") property.

### [Mouse events](#mouse_events "Permalink to Mouse events")

[`auxclick`](https://developer.mozilla.org/en-US/docs/Web/API/Element/auxclick_event "auxclick")  
Fired when a non-primary pointing device button (e.g., any mouse button other than the left button) has been pressed and released on an element.  
Also available via the [`onauxclick`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onauxclick "onauxclick") property.

[`click`](https://developer.mozilla.org/en-US/docs/Web/API/Element/click_event "click")  
Fired when a pointing device button (e.g., a mouse's primary button) is pressed and released on a single element.  
Also available via the [`onclick`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onclick "onclick") property.

[`contextmenu`](https://developer.mozilla.org/en-US/docs/Web/API/Element/contextmenu_event "contextmenu")  
Fired when the user attempts to open a context menu.  
Also available via the [`oncontextmenu`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oncontextmenu "oncontextmenu") property.

[`dblclick`](https://developer.mozilla.org/en-US/docs/Web/API/Element/dblclick_event "dblclick")  
Fired when a pointing device button (e.g., a mouse's primary button) is clicked twice on a single element.  
Also available via the [`ondblclick`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ondblclick "ondblclick") property.

[`DOMActivate`](https://developer.mozilla.org/en-US/docs/Web/API/Element/DOMActivate_event "DOMActivate")   
Occurs when an element is activated, for instance, through a mouse click or a keypress.

[`mousedown`](https://developer.mozilla.org/en-US/docs/Web/API/Element/mousedown_event "mousedown")  
Fired when a pointing device button is pressed on an element.  
Also available via the [`onmousedown`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmousedown "onmousedown") property.

[`mouseenter`](https://developer.mozilla.org/en-US/docs/Web/API/Element/mouseenter_event "mouseenter")  
Fired when a pointing device (usually a mouse) is moved over the element that has the listener attached.  
Also available via the [`onmouseenter`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmouseenter "onmouseenter") property.

[`mouseleave`](https://developer.mozilla.org/en-US/docs/Web/API/Element/mouseleave_event "mouseleave")  
Fired when the pointer of a pointing device (usually a mouse) is moved out of an element that has the listener attached to it.  
Also available via the [`onmouseleave`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmouseleave "onmouseleave") property.

[`mousemove`](https://developer.mozilla.org/en-US/docs/Web/API/Element/mousemove_event "mousemove")  
Fired when a pointing device (usually a mouse) is moved while over an element.  
Also available via the [`onmousemove`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmousemove "onmousemove") property.

[`mouseout`](https://developer.mozilla.org/en-US/docs/Web/API/Element/mouseout_event "mouseout")  
Fired when a pointing device (usually a mouse) is moved off the element to which the listener is attached or off one of its children.  
Also available via the [`onmouseout`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmouseout "onmouseout") property.

[`mouseover`](https://developer.mozilla.org/en-US/docs/Web/API/Element/mouseover_event "mouseover")  
Fired when a pointing device is moved onto the element to which the listener is attached or onto one of its children.  
Also available via the [`onmouseover`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmouseover "onmouseover") property.

[`mouseup`](https://developer.mozilla.org/en-US/docs/Web/API/Element/mouseup_event "mouseup")  
Fired when a pointing device button is released on an element.  
Also available via the [`onmouseup`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmouseup "onmouseup") property.

[`webkitmouseforcechanged`](https://developer.mozilla.org/en-US/docs/Web/API/Element/webkitmouseforcechanged_event "webkitmouseforcechanged")  
Fired each time the amount of pressure changes on the trackpadtouchscreen.

[`webkitmouseforcedown`](https://developer.mozilla.org/en-US/docs/Web/API/Element/webkitmouseforcedown_event "webkitmouseforcedown")  
Fired after the mousedown event as soon as sufficient pressure has been applied to qualify as a "force click".

[`webkitmouseforcewillbegin`](https://developer.mozilla.org/en-US/docs/Web/API/Element/webkitmouseforcewillbegin_event "webkitmouseforcewillbegin")  
Fired before the [`mousedown`](https://developer.mozilla.org/en-US/docs/Web/API/Element/mousedown_event "mousedown") event.

[`webkitmouseforceup`](https://developer.mozilla.org/en-US/docs/Web/API/Element/webkitmouseforceup_event "webkitmouseforceup")  
Fired after the [`webkitmouseforcedown`](https://developer.mozilla.org/en-US/docs/Web/API/Element/webkitmouseforcedown_event "webkitmouseforcedown") event as soon as the pressure has been reduced sufficiently to end the "force click".

### [Touch events](#touch_events "Permalink to Touch events")

[`touchcancel`](https://developer.mozilla.org/en-US/docs/Web/API/Element/touchcancel_event "touchcancel")  
Fired when one or more touch points have been disrupted in an implementation-specific manner (for example, too many touch points are created).  
Also available via the [`ontouchcancel`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ontouchcancel "ontouchcancel") property.

[`touchend`](https://developer.mozilla.org/en-US/docs/Web/API/Element/touchend_event "touchend")  
Fired when one or more touch points are removed from the touch surface.  
Also available via the [`ontouchend`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ontouchend "ontouchend") property

[`touchmove`](https://developer.mozilla.org/en-US/docs/Web/API/Element/touchmove_event "touchmove")  
Fired when one or more touch points are moved along the touch surface.  
Also available via the [`ontouchmove`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ontouchmove "ontouchmove") property

[`touchstart`](https://developer.mozilla.org/en-US/docs/Web/API/Element/touchstart_event "touchstart")  
Fired when one or more touch points are placed on the touch surface.  
Also available via the [`ontouchstart`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ontouchstart "ontouchstart") property

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/" class="external" title="The &#39;Web Animations&#39; specification">Web Animations</a></td><td><span class="spec-wd">Working Draft</span></td><td>Added the <code>getAnimations()</code> method.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/pointerevents2/#extensions-to-the-element-interface" class="external">Pointer Events – Level 2<br />
<span class="small">The definition of 'Element' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Added the following event handlers: <code>ongotpointercapture</code> and <code>onlostpointercapture</code>.<br />
Added the following methods: <code>setPointerCapture()</code> and <code>releasePointerCapture()</code>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/pointerevents1/#extensions-to-the-element-interface" class="external">Pointer Events<br />
<span class="small">The definition of 'Element' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Added the following event handlers: <code>ongotpointercapture</code> and <code>onlostpointercapture</code>.<br />
Added the following methods: <code>setPointerCapture()</code> and <code>releasePointerCapture()</code>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/selectors-api/#interface-definitions" class="external">Selectors API Level 1<br />
<span class="small">The definition of 'Element' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Added the following methods: <code>querySelector()</code> and <code>querySelectorAll()</code>.</td></tr><tr class="odd"><td><a href="https://w3c.github.io/pointerlock/#extensions-to-the-element-interface" class="external">Pointer Lock<br />
<span class="small">The definition of 'Element' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Added the <code>requestPointerLock()</code> method.</td></tr><tr class="even"><td><a href="https://fullscreen.spec.whatwg.org/#api" class="external">Fullscreen API<br />
<span class="small">The definition of 'Element' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Added the <code>requestFullscreen()</code> method.</td></tr><tr class="odd"><td><a href="https://w3c.github.io/DOM-Parsing/#extensions-to-the-element-interface" class="external">DOM Parsing and Serialization<br />
<span class="small">The definition of 'Element' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Added the following properties: <code>innerHTML</code>, and <code>outerHTML</code>.<br />
Added the following method: <code>insertAdjacentHTML()</code>.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/cssom-view/#extension-to-the-element-interface" class="external">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'Element' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Added the following properties: <code>scrollTop</code>, <code>scrollLeft</code>, <code>scrollWidth</code>, <code>scrollHeight</code>, <code>clientTop</code>, <code>clientLeft</code>, <code>clientWidth</code>, and <code>clientHeight</code>.<br />
Added the following methods: <code>getClientRects()</code>, <code>getBoundingClientRect()</code>, <code>scroll()</code>, <code>scrollBy()</code>, <code>scrollTo()</code> and <code>scrollIntoView()</code>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/ElementTraversal/#ecmascript-bindings" class="external">Element Traversal Specification<br />
<span class="small">The definition of 'Element' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Added inheritance of the <code>ElementTraversal</code> interface.</td></tr><tr class="even"><td><a href="https://dom.spec.whatwg.org/#interface-element" class="external">DOM<br />
<span class="small">The definition of 'Element' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Added the following methods: <code>closest()</code>, <code>insertAdjacentElement()</code> and <code>insertAdjacentText()</code>.<br />
Moved <code>hasAttributes()</code> from the <code>Node</code> interface to this one.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/dom/#interface-element" class="external">DOM4<br />
<span class="small">The definition of 'Element' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Removed the following methods: <code>setIdAttribute()</code>, <code>setIdAttributeNS()</code>, and <code>setIdAttributeNode()</code>.<br />
Modified the return value of <code>getElementsByTagName()</code> and <code>getElementsByTagNameNS()</code>.<br />
Removed the <code>schemaTypeInfo</code> property.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-3-Core/core.html#ID-745549614" class="external">Document Object Model (DOM) Level 3 Core Specification<br />
<span class="small">The definition of 'Element' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Added the following methods: <code>setIdAttribute()</code>, <code>setIdAttributeNS()</code>, and <code>setIdAttributeNode()</code>. These methods were never implemented and have been removed in later specifications.<br />
Added the <code>schemaTypeInfo</code> property. This property was never implemented and has been removed in later specifications.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Core/core.html#ID-745549614" class="external">Document Object Model (DOM) Level 2 Core Specification<br />
<span class="small">The definition of 'Element' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>The <code>normalize()</code> method has been moved to <a href="https://developer.mozilla.org/en-US/docs/Web/API/Node"><code>Node</code></a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-core.html#ID-745549614" class="external">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'Element' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/element/index.html "Folder: en-us/web/api/element (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FElement%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Felement%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FElement%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Felement%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F5394f9462d26e4f9ee38a12259311416d3fa1678%0A*+Document+last+modified%3A+2021-06-02T17%3A47%3A42.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22Element%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Jun 2, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/Element/contributors.txt)

Change your languageSelect your preferred language English (US)DeutschEspañolFrançais日本語한국어PolskiPortuguês (do Brasil)Русский中文 (简体)正體中文 (繁體)

Change language

#### Related Topics

1.  **[Document Object Model](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model)**
2.  **[`Element`](https://developer.mozilla.org/en-US/docs/Web/API/Element)**
3.  Properties
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
4.  Methods
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
5.  Events
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
    26. [`mousedown`](https://developer.mozilla.org/en-US/docs/Web/API/Element/mousedown_event)
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
6.  Inheritance:
    1.  [`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node)
    2.  [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)
7.  Related pages for DOM
    1.  [`AbortController`](https://developer.mozilla.org/en-US/docs/Web/API/AbortController)
    2.  [`AbortSignal`](https://developer.mozilla.org/en-US/docs/Web/API/AbortSignal)
    3.  [`AbstractRange`](https://developer.mozilla.org/en-US/docs/Web/API/AbstractRange)
    4.  [`Attr`](https://developer.mozilla.org/en-US/docs/Web/API/Attr)
    5.  [`ByteString`](https://developer.mozilla.org/en-US/docs/Web/API/ByteString)
    6.  [`CDATASection`](https://developer.mozilla.org/en-US/docs/Web/API/CDATASection)
    7.  [`CSSPrimitiveValue`](https://developer.mozilla.org/en-US/docs/Web/API/CSSPrimitiveValue)
    8.  [`CSSValue`](https://developer.mozilla.org/en-US/docs/Web/API/CSSValue)
    9.  [`CSSValueList`](https://developer.mozilla.org/en-US/docs/Web/API/CSSValueList)
    10. [`CharacterData`](https://developer.mozilla.org/en-US/docs/Web/API/CharacterData)
    11. [`ChildNode`](https://developer.mozilla.org/en-US/docs/Web/API/ChildNode)
    12. [`Comment`](https://developer.mozilla.org/en-US/docs/Web/API/Comment)
    13. [`CustomEvent`](https://developer.mozilla.org/en-US/docs/Web/API/CustomEvent)
    14. [`DOMConfiguration`](https://developer.mozilla.org/en-US/docs/Web/API/DOMConfiguration)
    15. [`DOMError`](https://developer.mozilla.org/en-US/docs/Web/API/DOMError)
    16. [`DOMErrorHandler`](https://developer.mozilla.org/en-US/docs/Web/API/DOMErrorHandler)
    17. [`DOMException`](https://developer.mozilla.org/en-US/docs/Web/API/DOMException)
    18. [`DOMImplementation`](https://developer.mozilla.org/en-US/docs/Web/API/DOMImplementation)
    19. [`DOMImplementationList`](https://developer.mozilla.org/en-US/docs/Web/API/DOMImplementationList)
    20. [`DOMImplementationRegistry`](https://developer.mozilla.org/en-US/docs/Web/API/DOMImplementationRegistry)
    21. [`DOMImplementationSource`](https://developer.mozilla.org/en-US/docs/Web/API/DOMImplementationSource)
    22. [`DOMLocator`](https://developer.mozilla.org/en-US/docs/Web/API/DOMLocator)
    23. [`DOMObject`](https://developer.mozilla.org/en-US/docs/Web/API/DOMObject)
    24. [`DOMParser`](https://developer.mozilla.org/en-US/docs/Web/API/DOMParser)
    25. [`DOMPoint`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPoint)
    26. [`DOMPointInit`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPointInit)
    27. [`DOMPointReadOnly`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPointReadOnly)
    28. [`DOMRect`](https://developer.mozilla.org/en-US/docs/Web/API/DOMRect)
    29. [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString)
    30. [`DOMTimeStamp`](https://developer.mozilla.org/en-US/docs/Web/API/DOMTimeStamp)
    31. [`DOMTokenList`](https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList)
    32. [`DOMUserData`](https://developer.mozilla.org/en-US/docs/Web/API/DOMUserData)
    33. [`Document`](https://developer.mozilla.org/en-US/docs/Web/API/Document)
    34. [`DocumentFragment`](https://developer.mozilla.org/en-US/docs/Web/API/DocumentFragment)
    35. [`DocumentType`](https://developer.mozilla.org/en-US/docs/Web/API/DocumentType)
    36. [`ElementTraversal`](https://developer.mozilla.org/en-US/docs/Web/API/ElementTraversal)
    37. [`Entity`](https://developer.mozilla.org/en-US/docs/Web/API/Entity)
    38. [`EntityReference`](https://developer.mozilla.org/en-US/docs/Web/API/EntityReference)
    39. [`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event)
    40. [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)
    41. [`HTMLCollection`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCollection)
    42. [`MutationObserver`](https://developer.mozilla.org/en-US/docs/Web/API/MutationObserver)
    43. [`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node)
    44. [`NodeFilter`](https://developer.mozilla.org/en-US/docs/Web/API/NodeFilter)
    45. [`NodeIterator`](https://developer.mozilla.org/en-US/docs/Web/API/NodeIterator)
    46. [`NodeList`](https://developer.mozilla.org/en-US/docs/Web/API/NodeList)
    47. [`ProcessingInstruction`](https://developer.mozilla.org/en-US/docs/Web/API/ProcessingInstruction)
    48. [`PromiseResolver`](https://developer.mozilla.org/en-US/docs/Web/API/PromiseResolver)
    49. [`Range`](https://developer.mozilla.org/en-US/docs/Web/API/Range)
    50. [`StaticRange`](https://developer.mozilla.org/en-US/docs/Web/API/StaticRange)
    51. [`Text`](https://developer.mozilla.org/en-US/docs/Web/API/Text)
    52. [`TextDecoder`](https://developer.mozilla.org/en-US/docs/Web/API/TextDecoder)
    53. [`TextEncoder`](https://developer.mozilla.org/en-US/docs/Web/API/TextEncoder)
    54. [`TimeRanges`](https://developer.mozilla.org/en-US/docs/Web/API/TimeRanges)
    55. [`TreeWalker`](https://developer.mozilla.org/en-US/docs/Web/API/TreeWalker)
    56. [`TypeInfo`](https://developer.mozilla.org/en-US/docs/Web/API/TypeInfo)
    57. [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString)
    58. [`UserDataHandler`](https://developer.mozilla.org/en-US/docs/Web/API/UserDataHandler)
    59. [`XMLDocument`](https://developer.mozilla.org/en-US/docs/Web/API/XMLDocument)

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
