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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/CharacterData" class="breadcrumb-current-page"><span data-property="name">CharacterData</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Properties](#properties)
-   [Methods](#methods)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

CharacterData
=============

The `CharacterData` abstract interface represents a [`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node) object that contains characters. This is an abstract interface, meaning there aren't any objects of type `CharacterData`: it is implemented by other interfaces like [`Text`](https://developer.mozilla.org/en-US/docs/Web/API/Text), [`Comment`](https://developer.mozilla.org/en-US/docs/Web/API/Comment), or [`ProcessingInstruction`](https://developer.mozilla.org/en-US/docs/Web/API/ProcessingInstruction), which aren't abstract.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

*`CharacterData` inherits properties from its parent, [`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node).*

[`CharacterData.data`](https://developer.mozilla.org/en-US/docs/Web/API/CharacterData/data)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) representing the textual data contained in this object.

[`CharacterData.length`](https://developer.mozilla.org/en-US/docs/Web/API/CharacterData/length) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns an `unsigned long` representing the size of the string contained in `CharacterData.data`.

[`Element.nextElementSibling`](https://developer.mozilla.org/en-US/docs/Web/API/Element/nextElementSibling) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the [`Element`](https://developer.mozilla.org/en-US/docs/Web/API/Element) immediately following the specified one in its parent's children list, or `null` if the specified element is the last one in the list.

[`Element.previousElementSibling`](https://developer.mozilla.org/en-US/docs/Web/API/Element/previousElementSibling) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the [`Element`](https://developer.mozilla.org/en-US/docs/Web/API/Element) immediately prior to the specified one in its parent's children list, or `null` if the specified element is the first one in the list.

[Methods](#methods "Permalink to Methods")
------------------------------------------

*`CharacterData` inherits methods from its parent, [`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node).*

[`CharacterData.appendData()`](https://developer.mozilla.org/en-US/docs/Web/API/CharacterData/appendData)  
Appends the given [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) to the `CharacterData.data` string; when this method returns, `data` contains the concatenated [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString).

[`CharacterData.deleteData()`](https://developer.mozilla.org/en-US/docs/Web/API/CharacterData/deleteData)  
Removes the specified amount of characters, starting at the specified offset, from the `CharacterData.data` string; when this method returns, `data` contains the shortened [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString).

[`CharacterData.insertData()`](https://developer.mozilla.org/en-US/docs/Web/API/CharacterData/insertData)  
Inserts the specified characters, at the specified offset, in the `CharacterData.data` string; when this method returns, `data` contains the modified [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString).

[`CharacterData.remove()`](https://developer.mozilla.org/en-US/docs/Web/API/CharacterData/remove)  
Removes the object from its parent children list.

[`CharacterData.replaceData()`](https://developer.mozilla.org/en-US/docs/Web/API/CharacterData/replaceData)  
Replaces the specified amount of characters, starting at the specified offset, with the specified [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString); when this method returns, `data` contains the modified [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString).

[`CharacterData.replaceWith()`](https://developer.mozilla.org/en-US/docs/Web/API/CharacterData/replaceWith)  
Replaces the characters in the children list of its parent with a set of [`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node) or [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) objects.

[`CharacterData.substringData()`](https://developer.mozilla.org/en-US/docs/Web/API/CharacterData/substringData)  
Returns a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) containing the part of `CharacterData.data` of the specified length and starting at the specified offset.

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#characterdata" class="external">DOM<br />
<span class="small">The definition of 'CharacterData' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Added implementation of the <a href="https://developer.mozilla.org/en-US/docs/Web/API/ChildNode"><code>ChildNode</code></a> and <a href="https://developer.mozilla.org/en-US/docs/Web/API/Element"><code>Element</code></a> interface.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-3-Core/core.html#ID-FF21A306" class="external">Document Object Model (DOM) Level 3 Core Specification<br />
<span class="small">The definition of 'CharacterData' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/DOM-Level-2-Core/" class="external" title="The &#39;Document Object Model (DOM) Level 2 Core Specification&#39; specification">Document Object Model (DOM) Level 2 Core Specification</a>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Core/core.html#ID-FF21A306" class="external">Document Object Model (DOM) Level 2 Core Specification<br />
<span class="small">The definition of 'CharacterData' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/REC-DOM-Level-1/" class="external" title="The &#39;Document Object Model (DOM) Level 1 Specification&#39; specification">Document Object Model (DOM) Level 1 Specification</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-core.html#ID-FF21A306" class="external">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'CharacterData' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [The DOM interfaces index](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model).

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/characterdata/index.html "Folder: en-us/web/api/characterdata (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FCharacterData%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fcharacterdata%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FCharacterData%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fcharacterdata%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fe085698aeab231f6d0c1d3bb7ea6288237946703%0A*+Document+last+modified%3A+2021-05-29T04%3A16%3A39.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22CharacterData%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 29, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/CharacterData/contributors.txt)

Change your languageSelect your preferred language English (US)Français日本語한국어Português (do Brasil)Русский中文 (简体)正體中文 (繁體)

Change language

#### Related Topics

1.  **[Document Object Model](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model)**
2.  **[`CharacterData`](https://developer.mozilla.org/en-US/docs/Web/API/CharacterData)**
3.  Methods
    1.  [`after()`](https://developer.mozilla.org/en-US/docs/Web/API/ChildNode/after)
    2.  [`appendData()`](https://developer.mozilla.org/en-US/docs/Web/API/CharacterData/appendData)
    3.  [`before()`](https://developer.mozilla.org/en-US/docs/Web/API/ChildNode/before)
    4.  [`data`](https://developer.mozilla.org/en-US/docs/Web/API/CharacterData/data)
    5.  [`deleteData()`](https://developer.mozilla.org/en-US/docs/Web/API/CharacterData/deleteData)
    6.  [`insertData()`](https://developer.mozilla.org/en-US/docs/Web/API/CharacterData/insertData)
    7.  [`length`](https://developer.mozilla.org/en-US/docs/Web/API/CharacterData/length)
    8.  [`remove()`](https://developer.mozilla.org/en-US/docs/Web/API/CharacterData/remove)
    9.  [`replaceData()`](https://developer.mozilla.org/en-US/docs/Web/API/CharacterData/replaceData)
    10. [`replaceWith()`](https://developer.mozilla.org/en-US/docs/Web/API/CharacterData/replaceWith)
    11. [`substringData()`](https://developer.mozilla.org/en-US/docs/Web/API/CharacterData/substringData)
4.  Inheritance:
    1.  [`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node)
    2.  [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)
5.  Related pages for DOM
    1.  [`AbortController`](https://developer.mozilla.org/en-US/docs/Web/API/AbortController)
    2.  [`AbortSignal`](https://developer.mozilla.org/en-US/docs/Web/API/AbortSignal)
    3.  [`AbstractRange`](https://developer.mozilla.org/en-US/docs/Web/API/AbstractRange)
    4.  [`Attr`](https://developer.mozilla.org/en-US/docs/Web/API/Attr)
    5.  [`ByteString`](https://developer.mozilla.org/en-US/docs/Web/API/ByteString)
    6.  [`CDATASection`](https://developer.mozilla.org/en-US/docs/Web/API/CDATASection)
    7.  [`CSSPrimitiveValue`](https://developer.mozilla.org/en-US/docs/Web/API/CSSPrimitiveValue)
    8.  [`CSSValue`](https://developer.mozilla.org/en-US/docs/Web/API/CSSValue)
    9.  [`CSSValueList`](https://developer.mozilla.org/en-US/docs/Web/API/CSSValueList)
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
