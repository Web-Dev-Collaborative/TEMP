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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList" class="breadcrumb-current-page"><span data-property="name">DOMTokenList</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Properties](#properties)
-   [Methods](#methods)
-   [Examples](#examples)
-   [Trimming of whitespace and removal of duplicates](#trimming_of_whitespace_and_removal_of_duplicates)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)

DOMTokenList
============

<span class="seoSummary">The `DOMTokenList` interface represents a set of space-separated tokens. Such a set is returned by [`Element.classList`](https://developer.mozilla.org/en-US/docs/Web/API/Element/classList), [`HTMLLinkElement.relList`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLLinkElement/relList), [`HTMLAnchorElement.relList`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAnchorElement/relList), [`HTMLAreaElement.relList`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/relList), <span class="page-not-created">`HTMLIframeElement.sandbox`</span>, or <span class="page-not-created">`HTMLOutputElement.htmlFor`</span>. It is indexed beginning with `0` as with JavaScript [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) objects. `DOMTokenList` is always case-sensitive.</span>

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

[`DOMTokenList.length`](https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/length) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Is an `integer` representing the number of objects stored in the object.

[`DOMTokenList.value`](https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/value)  
A stringifier property that returns the value of the list as a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString).

[Methods](#methods "Permalink to Methods")
------------------------------------------

[`DOMTokenList.item(index)`](https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/item "DOMTokenList.item(<var>index</var>)")  
Returns the item in the list by its `index`, or `undefined` if `index` is greater than or equal to the list's `length`.

[`DOMTokenList.contains(token)`](https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/contains "DOMTokenList.contains(<var>token</var>)")  
Returns `true` if the list contains the given `token`, otherwise `false`.

[`DOMTokenList.add(token1[, token2[, ...tokenN]])`](https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/add "DOMTokenList.add(<var>token1</var>[, <var>token2</var>[, ...<var>tokenN</var>]])")  
Adds the specified `token`(s) to the list.

[`DOMTokenList.remove(token1[, token2[, ...tokenN]])`](https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/remove "DOMTokenList.remove(<var>token1</var>[, <var>token2</var>[, ...<var>tokenN</var>]])")  
Removes the specified `token`(s) from the list.

[`DOMTokenList.replace(oldToken, newToken)`](https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/replace "DOMTokenList.replace(<var>oldToken</var>, <var>newToken</var>)")  
Replaces `token` with `newToken`.

[`DOMTokenList.supports(token)`](https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/supports "DOMTokenList.supports(<var>token</var>)")  
Returns `true` if a given `token` is in the associated attribute's supported tokens.

[`DOMTokenList.toggle(token [, force])`](https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/toggle "DOMTokenList.toggle(<var>token</var> [, <var>force</var>])")  
Removes `token` from the list if it exists, or adds `token` to the list if it doesn't. Returns a boolean indicating whether `token` is in the list after the operation.

[`DOMTokenList.entries()`](https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/entries)  
Returns an [iterator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols), allowing you to go through all key/value pairs contained in this object.

[`DOMTokenList.forEach(callback [, thisArg])`](https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/forEach "DOMTokenList.forEach(<var>callback</var> [, <var>thisArg</var>])")  
Executes a provided `callback` function once per `DOMTokenList` element.

[`DOMTokenList.keys()`](https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/keys)  
Returns an [iterator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols), allowing you to go through all keys of the key/value pairs contained in this object.

[`DOMTokenList.values()`](https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/values)  
Returns an [iterator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols), allowing you to go through all values of the key/value pairs contained in this object.

[Examples](#examples "Permalink to Examples")
---------------------------------------------

In the following simple example, we retrieve the list of classes set on a [`<p>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p) element as a `DOMTokenList` using [`Element.classList`](https://developer.mozilla.org/en-US/docs/Web/API/Element/classList), add a class using [`DOMTokenList.add()`](https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/add), and then update the [`Node.textContent`](https://developer.mozilla.org/en-US/docs/Web/API/Node/textContent) of the `<p>` to equal the `DOMTokenList`.

First, the HTML:

    <p class="a b c"></p>

Now the JavaScript:

    let para = document.querySelector("p");
    let classes = para.classList;
    para.classList.add("d");
    para.textContent = `paragraph classList is "${classes}"`;

The output looks like this:

[Trimming of whitespace and removal of duplicates](#trimming_of_whitespace_and_removal_of_duplicates "Permalink to Trimming of whitespace and removal of duplicates")
---------------------------------------------------------------------------------------------------------------------------------------------------------------------

Methods that modify the `DOMTokenList` (such as [`DOMTokenList.add()`](https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/add)) automatically trim any excess [Whitespace](https://developer.mozilla.org/en-US/docs/Glossary/Whitespace) and remove duplicate values from the list. For example:

    <span class="    d   d e f"></span>

    let span = document.querySelector("span");
    let classes = span.classList;
    span.classList.add("x");
    span.textContent = `span classList is "${classes}"`;

The output looks like this:

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#interface-domtokenlist" class="external">DOM<br />
<span class="small">The definition of 'DOMTokenList' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/domtokenlist/index.html "Folder: en-us/web/api/domtokenlist (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FDOMTokenList%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fdomtokenlist%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FDOMTokenList%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fdomtokenlist%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Ffffe339bce9adcb9ced09d1d5eff291c105ce6ad%0A*+Document+last+modified%3A+2021-05-29T05%3A32%3A06.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22DOMTokenList%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 29, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/contributors.txt)

Change your languageSelect your preferred language English (US)DeutschFrançais日本語한국어Русский中文 (简体)正體中文 (繁體)

Change language

#### Related Topics

1.  **[Document Object Model](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model)**
2.  **[`DOMTokenList`](https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList)**
3.  Properties
    1.  [`length`](https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/length)
    2.  [`value`](https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/value)
4.  Methods
    1.  [`add()`](https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/add)
    2.  [`contains()`](https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/contains)
    3.  [`entries()`](https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/entries)
    4.  [`forEach()`](https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/forEach)
    5.  [`item()`](https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/item)
    6.  [`keys()`](https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/keys)
    7.  [`remove()`](https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/remove)
    8.  [`replace()`](https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/replace)
    9.  [`supports()`](https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/supports)
    10. [`toggle()`](https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/toggle)
    11. [`values()`](https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/values)
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
-   [Terms](https://www.mozilla.org/about/legal/terms/mozilla)
-   [Privacy](https://www.mozilla.org/privacy/websites/)
-   [Cookies](https://www.mozilla.org/privacy/websites/#cookies)
