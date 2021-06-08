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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMException" class="breadcrumb-current-page"><span data-property="name">DOMException</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Constructor](#constructor)
-   [Properties](#properties)
-   [Error names](#error_names)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

DOMException
============

<span class="seoSummary">The `DOMException` interface represents an abnormal event (called an **exception**) that occurs as a result of calling a method or accessing a property of a web API.</span> This is basically how error conditions are described in web APIs.

Each exception has a **name**, which is a short "PascalCase"-style string identifying the error or abnormal condition.

[Constructor](#constructor "Permalink to Constructor")
------------------------------------------------------

[`DOMException()`](https://developer.mozilla.org/en-US/docs/Web/API/DOMException/DOMException "DOMException()")   
Returns a `DOMException` object with a specified message and name.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

[`DOMException.code`](https://developer.mozilla.org/en-US/docs/Web/API/DOMException/code) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a `short` that contains one of the error code constants, or `0` if none match. This field is used for historical reasons. New DOM exceptions don't use this anymore: they put this info in the [`DOMException.name`](https://developer.mozilla.org/en-US/docs/Web/API/DOMException/name) attribute.

[`DOMException.message`](https://developer.mozilla.org/en-US/docs/Web/API/DOMException/message) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) representing a message or description associated with the given [error name](https://developer.mozilla.org/en-US/docs/Web/API/DOMException#error_names).

[`DOMException.name`](https://developer.mozilla.org/en-US/docs/Web/API/DOMException/name) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) that contains one of the strings associated with an [error name](#error_names).

[Error names](#error_names "Permalink to Error names")
------------------------------------------------------

Common error names are listed here. Some APIs define their own sets of names, so this is not necessarily a complete list.

**Note**: Because historically the errors were identified by a numeric value that corresponded with a named variable defined to have that value, some of the entries below indicate the legacy code value and constant name that were used in the past.

<span id="exception-IndexSizeError">`IndexSizeError`</span>  
The index is not in the allowed range. For example, this can be thrown by the [`Range`](https://developer.mozilla.org/en-US/docs/Web/API/Range) object. (Legacy code value: `1` and legacy constant name: `INDEX_SIZE_ERR`)

`HierarchyRequestError`  
The node tree hierarchy is not correct. (Legacy code value: `3` and legacy constant name: `HIERARCHY_REQUEST_ERR`)

<span id="exception-WrongDocumentError">`WrongDocumentError`</span>  
The object is in the wrong [`Document`](https://developer.mozilla.org/en-US/docs/Web/API/Document). (Legacy code value: `4` and legacy constant name: `WRONG_DOCUMENT_ERR`)

<span id="exception-InvalidCharacterError">`InvalidCharacterError`</span>  
The string contains invalid characters. (Legacy code value: `5` and legacy constant name: `INVALID_CHARACTER_ERR`)

<span id="exception-NoModificationAllowedError">`NoModificationAllowedError`</span>  
The object cannot be modified. (Legacy code value: `7` and legacy constant name: `NO_MODIFICATION_ALLOWED_ERR`)

<span id="exception-NotFoundError">`NotFoundError`</span>  
The object cannot be found here. (Legacy code value: `8` and legacy constant name: `NOT_FOUND_ERR`)

<span id="exception-NotSupportedError">`NotSupportedError`</span>  
The operation is not supported. (Legacy code value: `9` and legacy constant name: `NOT_SUPPORTED_ERR`)

<span id="exception-InvalidStateError">`InvalidStateError`</span>  
The object is in an invalid state. (Legacy code value: `11` and legacy constant name: `INVALID_STATE_ERR`)

<span id="exception-SyntaxError">`SyntaxError`</span>  
The string did not match the expected pattern. (Legacy code value: `12` and legacy constant name: `SYNTAX_ERR`)

<span id="exception-InvalidModificationError">`InvalidModificationError`</span>  
The object cannot be modified in this way. (Legacy code value: `13` and legacy constant name: `INVALID_MODIFICATION_ERR`)

<span id="exception-NamespaceError">`NamespaceError`</span>  
The operation is not allowed by Namespaces in XML. (Legacy code value: `14` and legacy constant name: `NAMESPACE_ERR`)

<span id="exception-InvalidAccessError">`InvalidAccessError`</span>  
The object does not support the operation or argument. (Legacy code value: `15` and legacy constant name: `INVALID_ACCESS_ERR`)

<span id="exception-TypeMismatchError">`TypeMismatchError`</span>   
The type of the object does not match the expected type. (Legacy code value: `17` and legacy constant name: `TYPE_MISMATCH_ERR`) This value is deprecated; the JavaScript [`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError) exception is now raised instead of a `DOMException` with this value.

<span id="exception-SecurityError">`SecurityError`</span>  
The operation is insecure. (Legacy code value: `18` and legacy constant name: `SECURITY_ERR`)

<span id="exception-NetworkError">`NetworkError`</span>   
A network error occurred. (Legacy code value: `19` and legacy constant name: `NETWORK_ERR`)

<span id="exception-AbortError">`AbortError`</span>   
The operation was aborted. (Legacy code value: `20` and legacy constant name: `ABORT_ERR`)

<span id="exception-URLMismatchError">`URLMismatchError`</span>   
The given URL does not match another URL. (Legacy code value: `21` and legacy constant name: `URL_MISMATCH_ERR`)

<span id="exception-QuotaExceededError">`QuotaExceededError`</span>   
The quota has been exceeded. (Legacy code value: `22` and legacy constant name: `QUOTA_EXCEEDED_ERR`)

<span id="exception-TimeoutError">`TimeoutError`</span>  
The operation timed out. (Legacy code value: `23` and legacy constant name: `TIMEOUT_ERR`)

<span id="exception-InvalidNodeTypeError">`InvalidNodeTypeError`</span>   
The node is incorrect or has an incorrect ancestor for this operation. (Legacy code value: `24` and legacy constant name: `INVALID_NODE_TYPE_ERR`)

<span id="exception-DataCloneError">`DataCloneError`</span>   
The object can not be cloned. (Legacy code value: `25` and legacy constant name: `DATA_CLONE_ERR`)

<span id="exception-EncodingError">`EncodingError`</span>   
The encoding or decoding operation failed (No legacy code value and constant name).

<span id="exception-NotReadableError">`NotReadableError`</span>   
The input/output read operation failed (No legacy code value and constant name).

<span id="exception-UnknownError">`UnknownError`</span>   
The operation failed for an unknown transient reason (e.g. out of memory) (No legacy code value and constant name).

<span id="exception-ConstraintError">`ConstraintError`</span>   
A mutation operation in a transaction failed because a constraint was not satisfied (No legacy code value and constant name).

<span id="exception-DataError">`DataError`</span>   
Provided data is inadequate (No legacy code value and constant name).

<span id="exception-TransactionInactiveError">`TransactionInactiveError`</span>   
A request was placed against a transaction that is currently not active or is finished (No legacy code value and constant name).

<span id="exception-ReadOnlyError">`ReadOnlyError`</span>   
The mutating operation was attempted in a "readonly" transaction (No legacy code value and constant name).

<span id="exception-VersionError">`VersionError`</span>   
An attempt was made to open a database using a lower version than the existing version (No legacy code value and constant name).

<span id="exception-OperationError">`OperationError`</span>   
The operation failed for an operation-specific reason (No legacy code value and constant name).

<span id="exception-NotAllowedError">`NotAllowedError`</span>  
The request is not allowed by the user agent or the platform in the current context, possibly because the user denied permission (No legacy code value and constant name).

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://heycam.github.io/webidl/#idl-DOMException" class="external">Web IDL<br />
<span class="small">The definition of 'constructor' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Adds the constructor for the <code>DOMException</code> class. Adds the <code>NotReadableError</code>, <code>UnknownError</code>, <code>ConstraintError</code>, <code>DataError</code>, <code>TransactionInactiveError</code>, <code>ReadOnlyError</code>, <code>VersionError</code>, <code>OperationError</code>, and <code>NotAllowedError</code> values.</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [`DOMError`](https://developer.mozilla.org/en-US/docs/Web/API/DOMError)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/domexception/index.html "Folder: en-us/web/api/domexception (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FDOMException%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fdomexception%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FDOMException%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fdomexception%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Ffffe339bce9adcb9ced09d1d5eff291c105ce6ad%0A*+Document+last+modified%3A+2021-05-29T05%3A32%3A06.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22DOMException%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 29, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/DOMException/contributors.txt)

Change your languageSelect your preferred language English (US)Français日本語Português (do Brasil)中文 (简体)

Change language

#### Related Topics

1.  **[Document Object Model](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model)**
2.  **[`DOMException`](https://developer.mozilla.org/en-US/docs/Web/API/DOMException)**
3.  Constructor
    1.  [`DOMException()`](https://developer.mozilla.org/en-US/docs/Web/API/DOMException/DOMException)
4.  Properties
    1.  [`code`](https://developer.mozilla.org/en-US/docs/Web/API/DOMException/code)
    2.  [`message`](https://developer.mozilla.org/en-US/docs/Web/API/DOMException/message)
    3.  [`name`](https://developer.mozilla.org/en-US/docs/Web/API/DOMException/name)
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
-   [Terms](https://www.mozilla.org/about/legal/terms/mozilla)
-   [Privacy](https://www.mozilla.org/privacy/websites/)
-   [Cookies](https://www.mozilla.org/privacy/websites/#cookies)
