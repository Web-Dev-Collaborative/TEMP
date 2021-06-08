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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/Attr" class="breadcrumb-current-page"><span data-property="name">Attr</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Properties](#properties)
-   [Deprecated properties and methods](#deprecated_properties_and_methods)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)

Attr
====

The `Attr` interface represents one of a DOM element's attributes as an object. In most DOM methods, you will directly retrieve the attribute as a string (e.g., [`Element.getAttribute()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/getAttribute)), but certain functions (e.g., [`Element.getAttributeNode()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/getAttributeNode)) or means of iterating return `Attr` types.

**Warning:** Starting in Gecko 7.0 (Firefox 7.0 / Thunderbird 7.0 / SeaMonkey 2.4), a number of deprecated properties and methods output warning messages to the console. You should revise your code accordingly. See [Deprecated properties and methods](#deprecated_properties_and_methods) for a complete list.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

 <span class="page-not-created">`name`</span> <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
The attribute's name.

 [`namespaceURI`](https://developer.mozilla.org/en-US/docs/Web/API/Attr/namespaceURI "namespaceURI") <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) representing the namespace URI of the attribute, or `null` if there is no namespace.

 [`localName`](https://developer.mozilla.org/en-US/docs/Web/API/Attr/localName "localName") <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) representing the local part of the qualified name of the attribute.

 [`prefix`](https://developer.mozilla.org/en-US/docs/Web/API/Attr/prefix "prefix") <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) representing the namespace prefix of the attribute, or `null` if no prefix is specified.

 <span class="page-not-created">`ownerElement`</span> <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
The element holding the attribute.

**Note:** DOM Level 4 removed this property. The assumption was that since you get an `Attr` object from an [`Element`](https://developer.mozilla.org/en-US/docs/Web/API/Element), you should already know the associated element.  
As that doesn't hold true in cases like `Attr` objects being returned by [`Document.evaluate`](https://developer.mozilla.org/en-US/docs/Web/API/Document/evaluate), the DOM Living Standard reintroduced the property.

Gecko outputs a deprecation note starting from Gecko 7.0 (Firefox 7.0 / Thunderbird 7.0 / SeaMonkey 2.4). This note was removed again in Gecko 49.0 (Firefox 49.0 / Thunderbird 49.0 / SeaMonkey 2.46).

 <span class="page-not-created">`specified`</span> <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
This property always returns `true`. Originally, it returned `true `if the attribute was explicitly specified in the source code or by a script, and `false` if its value came from the default one defined in the document's DTD.

 <span class="page-not-created">`value`</span>   
The attribute's value.

[Deprecated properties and methods](#deprecated_properties_and_methods "Permalink to Deprecated properties and methods")
------------------------------------------------------------------------------------------------------------------------

The following properties have been deprecated. Where available, the appropriate replacement is noted.

`attributes`  
This property now always returns `NULL`.

 `childNodes`   
This property now always returns an empty [`NodeList`](https://developer.mozilla.org/en-US/docs/Web/API/NodeList).

 `firstChild`   
This property now always returns `NULL`.

 `isId` <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
Indicates whether the attribute is an "ID attribute". An "ID attribute" being an attribute which value is expected to be unique across a DOM Document. In HTML DOM, "id" is the only ID attribute, but XML documents could define others. Whether or not an attribute is unique is often determined by a [DTD](https://developer.mozilla.org/en-US/docs/Glossary/Doctype) or other schema description.

 `lastChild`   
This property now always returns `NULL`.

`nextSibling`  
This property now always returns `NULL`.

`nodeName`  
Use <span class="page-not-created">`Attr.name`</span> instead.

`nodeType`  
This property now always returns 2 (`ATTRIBUTE_NODE`).

`nodeValue`  
Use <span class="page-not-created">`Attr.value`</span> instead.

`ownerDocument`  
You shouldn't have been using this in the first place, so you probably don't care that this is going away.

`parentNode`  
This property now always returns `NULL`.

`previousSibling`  
This property now always returns `NULL`.

 `schemaTypeInfo` <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
The type information associated with this attribute. While the type information contained in this attribute is guaranteed to be correct after loading the document or invoking <span class="page-not-created">`Document.normalizeDocument`</span>, this property may not be reliable if the node was moved.

`specified`  
This property now always returns `true`.

`textContent`  
Use <span class="page-not-created">`Attr.value`</span> instead.

The following methods have been deprecated:

 `appendChild()`   
Modify the value of <span class="page-not-created">`Attr.value`</span> instead.

`cloneNode()`  
You shouldn't have been using this in the first place, so you probably don't care that this is going away.

`createAttribute()`  
Use [`Element.setAttribute()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/setAttribute) instead.

`createAttributeNS()`  
Use [`Element.setAttributeNS()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/setAttributeNS) instead.

`getAttributeNode()`  
Use [`Element.getAttribute()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/getAttribute) instead.

`getAttributeNodeNS()`  
Use [`Element.getAttributeNS()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/getAttributeNS) instead.

 `hasAttributes()`   
This method now always returns false.

`hasChildNodes()`  
This method now always returns false.

`insertBefore()`  
Modify the value of <span class="page-not-created">`Attr.value`</span> instead.

`isSupported()`  
You shouldn't have been using this in the first place, so you probably don't care that this is going away.

`isEqualNode()`  
You shouldn't have been using this in the first place, so you probably don't care that this is going away.

`normalize()`  
You shouldn't have been using this in the first place, so you probably don't care that this is going away.

`removeAttributeNode()`  
Use [`Element.removeAttribute()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/removeAttribute) instead.

 `removeChild()`   
Modify the value of <span class="page-not-created">`Attr.value`</span> instead.

 `replaceChild()`   
Modify the value of <span class="page-not-created">`Attr.value`</span> instead.

`setAttributeNode()`  
Use [`Element.setAttribute()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/setAttribute) instead.

`setAttributeNodeNS()`  
Use [`Element.setAttributeNS()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/setAttributeNS) instead.

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#interface-attr" class="external">DOM<br />
<span class="small">The definition of 'Attr' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Added <code>ownerElement</code> property back</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/dom/#interface-attr" class="external">DOM4<br />
<span class="small">The definition of 'Attr' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Moved <code>namespaceURI</code>, <code>prefix</code> and <code>localName</code> from <a href="https://developer.mozilla.org/en-US/docs/Web/API/Node"><code>Node</code></a> to this API and removed <code>ownerElement</code>, <code>schemaTypeInfo</code> and <code>isId</code>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-3-Core/core.html#ID-637646024" class="external">Document Object Model (DOM) Level 3 Core Specification<br />
<span class="small">The definition of 'Attr' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/attr/index.html "Folder: en-us/web/api/attr (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAttr%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fattr%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAttr%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fattr%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fc141b2c35a21ca911a3dc050de0d77695873dba5%0A*+Document+last+modified%3A+2021-05-29T02%3A55%3A10.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22Attr%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 29, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/Attr/contributors.txt)

Change your language Select your preferred language English (US) Español Français 日本語 Polski Português (do Brasil) Русский 中文 (简体)

Change language

#### Related Topics

1.  **[Document Object Model](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model)**
2.  **[`Attr`](https://developer.mozilla.org/en-US/docs/Web/API/Attr)**
3.  Properties
    1.  [`localName`](https://developer.mozilla.org/en-US/docs/Web/API/Attr/localName)
    2.  [`namespaceURI`](https://developer.mozilla.org/en-US/docs/Web/API/Attr/namespaceURI)
    3.  [`prefix`](https://developer.mozilla.org/en-US/docs/Web/API/Attr/prefix)
4.  Inheritance:
    1.  [`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node)
    2.  [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)
5.  Related pages for DOM
    1.  [`AbortController`](https://developer.mozilla.org/en-US/docs/Web/API/AbortController)
    2.  [`AbortSignal`](https://developer.mozilla.org/en-US/docs/Web/API/AbortSignal)
    3.  [`AbstractRange`](https://developer.mozilla.org/en-US/docs/Web/API/AbstractRange)
    4.  [`ByteString`](https://developer.mozilla.org/en-US/docs/Web/API/ByteString)
    5.  [`CDATASection`](https://developer.mozilla.org/en-US/docs/Web/API/CDATASection)
    6.  [`CSSPrimitiveValue`](https://developer.mozilla.org/en-US/docs/Web/API/CSSPrimitiveValue)
    7.  [`CSSValue`](https://developer.mozilla.org/en-US/docs/Web/API/CSSValue)
    8.  [`CSSValueList`](https://developer.mozilla.org/en-US/docs/Web/API/CSSValueList)
    9.  [`CharacterData`](https://developer.mozilla.org/en-US/docs/Web/API/CharacterData)
    10. [`ChildNode`](https://developer.mozilla.org/en-US/docs/Web/API/ChildNode)
    11. [`Comment`](https://developer.mozilla.org/en-US/docs/Web/API/Comment)
    12. [`CustomEvent`](https://developer.mozilla.org/en-US/docs/Web/API/CustomEvent)
    13. [`DOMConfiguration`](https://developer.mozilla.org/en-US/docs/Web/API/DOMConfiguration)
    14. [`DOMError`](https://developer.mozilla.org/en-US/docs/Web/API/DOMError)
    15. [`DOMErrorHandler`](https://developer.mozilla.org/en-US/docs/Web/API/DOMErrorHandler)
    16. [`DOMException`](https://developer.mozilla.org/en-US/docs/Web/API/DOMException)
    17. [`DOMImplementation`](https://developer.mozilla.org/en-US/docs/Web/API/DOMImplementation)
    18. [`DOMImplementationList`](https://developer.mozilla.org/en-US/docs/Web/API/DOMImplementationList)
    19. [`DOMImplementationRegistry`](https://developer.mozilla.org/en-US/docs/Web/API/DOMImplementationRegistry)
    20. [`DOMImplementationSource`](https://developer.mozilla.org/en-US/docs/Web/API/DOMImplementationSource)
    21. [`DOMLocator`](https://developer.mozilla.org/en-US/docs/Web/API/DOMLocator)
    22. [`DOMObject`](https://developer.mozilla.org/en-US/docs/Web/API/DOMObject)
    23. [`DOMParser`](https://developer.mozilla.org/en-US/docs/Web/API/DOMParser)
    24. [`DOMPoint`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPoint)
    25. [`DOMPointInit`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPointInit)
    26. [`DOMPointReadOnly`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPointReadOnly)
    27. [`DOMRect`](https://developer.mozilla.org/en-US/docs/Web/API/DOMRect)
    28. [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString)
    29. [`DOMTimeStamp`](https://developer.mozilla.org/en-US/docs/Web/API/DOMTimeStamp)
    30. [`DOMTokenList`](https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList)
    31. [`DOMUserData`](https://developer.mozilla.org/en-US/docs/Web/API/DOMUserData)
    32. [`Document`](https://developer.mozilla.org/en-US/docs/Web/API/Document)
    33. [`DocumentFragment`](https://developer.mozilla.org/en-US/docs/Web/API/DocumentFragment)
    34. [`DocumentType`](https://developer.mozilla.org/en-US/docs/Web/API/DocumentType)
    35. [`Element`](https://developer.mozilla.org/en-US/docs/Web/API/Element)
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
