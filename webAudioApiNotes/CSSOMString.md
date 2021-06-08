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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSOMString" class="breadcrumb-current-page"><span data-property="name">CSSOMString</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Specifications](#specifications)
-   [See also](#see_also)

CSSOMString
===========

**`CSSOMString`** is used to denote string data in [CSSOM](https://developer.mozilla.org/en-US/docs/Web/API/CSS_Object_Model) specifications and can refer to either [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) or [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString). When a specification says `CSSOMString`, it depends on the browser vendors to choose whether to use `DOMString` or `USVString`. While browser implementations that use UTF-8 internally to represent strings in memory can use `USVString` when the specification says `CSSOMString`, implementations that already represent strings as 16-bit sequences might choose to use `DOMString` instead.

#### Implementation differences

<table><tbody><tr class="odd"><td>Browser</td><td>DOMString or USVString for CSSOMString</td></tr><tr class="even"><td>Firefox (Gecko)</td><td>USVString</td></tr><tr class="odd"><td>Chrome (Blink)</td><td>USVString</td></tr><tr class="even"><td>Safari (WebKit)</td><td>USVString</td></tr><tr class="odd"><td>Edge (EdgeHTML)</td><td>-</td></tr><tr class="even"><td>Opera (Blink)</td><td>USVString</td></tr></tbody></table>

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#cssomstring-type" class="external">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'CSSOMString' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)
-   [`CSS_Object_Model`](https://developer.mozilla.org/en-US/docs/Web/API/CSS_Object_Model)
-   [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString)
-   [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString)
-   [Binary strings](https://developer.mozilla.org/en-US/docs/Web/API/DOMString/Binary)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/cssomstring/index.html "Folder: en-us/web/api/cssomstring (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FCSSOMString%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fcssomstring%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FCSSOMString%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fcssomstring%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fd5cf56f90ed1268223b96501149a7ca40b276438%0A*+Document+last+modified%3A+2021-02-04T10%3A39%3A33.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22CSSOMString%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Feb 4, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/CSSOMString/contributors.txt)

Change your languageSelect your preferred language English (US)日本語한국어

Change language

#### Related Topics

1.  **[Document Object Model](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model)**
2.  **[`CSSOMString`](https://developer.mozilla.org/en-US/docs/Web/API/CSSOMString)**
3.  Related pages for DOM
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
    36. [`Element`](https://developer.mozilla.org/en-US/docs/Web/API/Element)
    37. [`ElementTraversal`](https://developer.mozilla.org/en-US/docs/Web/API/ElementTraversal)
    38. [`Entity`](https://developer.mozilla.org/en-US/docs/Web/API/Entity)
    39. [`EntityReference`](https://developer.mozilla.org/en-US/docs/Web/API/EntityReference)
    40. [`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event)
    41. [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)
    42. [`HTMLCollection`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCollection)
    43. [`MutationObserver`](https://developer.mozilla.org/en-US/docs/Web/API/MutationObserver)
    44. [`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node)
    45. [`NodeFilter`](https://developer.mozilla.org/en-US/docs/Web/API/NodeFilter)
    46. [`NodeIterator`](https://developer.mozilla.org/en-US/docs/Web/API/NodeIterator)
    47. [`NodeList`](https://developer.mozilla.org/en-US/docs/Web/API/NodeList)
    48. [`ProcessingInstruction`](https://developer.mozilla.org/en-US/docs/Web/API/ProcessingInstruction)
    49. [`PromiseResolver`](https://developer.mozilla.org/en-US/docs/Web/API/PromiseResolver)
    50. [`Range`](https://developer.mozilla.org/en-US/docs/Web/API/Range)
    51. [`StaticRange`](https://developer.mozilla.org/en-US/docs/Web/API/StaticRange)
    52. [`Text`](https://developer.mozilla.org/en-US/docs/Web/API/Text)
    53. [`TextDecoder`](https://developer.mozilla.org/en-US/docs/Web/API/TextDecoder)
    54. [`TextEncoder`](https://developer.mozilla.org/en-US/docs/Web/API/TextEncoder)
    55. [`TimeRanges`](https://developer.mozilla.org/en-US/docs/Web/API/TimeRanges)
    56. [`TreeWalker`](https://developer.mozilla.org/en-US/docs/Web/API/TreeWalker)
    57. [`TypeInfo`](https://developer.mozilla.org/en-US/docs/Web/API/TypeInfo)
    58. [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString)
    59. [`UserDataHandler`](https://developer.mozilla.org/en-US/docs/Web/API/UserDataHandler)
    60. [`XMLDocument`](https://developer.mozilla.org/en-US/docs/Web/API/XMLDocument)

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
