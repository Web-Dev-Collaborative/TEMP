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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/AbortController" class="breadcrumb-current-page"><span data-property="name">AbortController</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Constructor](#constructor)
-   [Properties](#properties)
-   [Methods](#methods)
-   [Examples](#examples)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

AbortController
===============

The **`AbortController`** interface represents a controller object that allows you to abort one or more Web requests as and when desired.

You can create a new `AbortController` object using the [`AbortController.AbortController()`](https://developer.mozilla.org/en-US/docs/Web/API/AbortController/AbortController) constructor. Communicating with a DOM request is done using an [`AbortSignal`](https://developer.mozilla.org/en-US/docs/Web/API/AbortSignal) object.

[Constructor](#constructor "Permalink to Constructor")
------------------------------------------------------

 [`AbortController()`](https://developer.mozilla.org/en-US/docs/Web/API/AbortController)   
Creates a new `AbortController` object instance.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

 [`AbortController.signal`](https://developer.mozilla.org/en-US/docs/Web/API/AbortController/signal) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
Returns a [`AbortSignal`](https://developer.mozilla.org/en-US/docs/Web/API/AbortSignal) object instance, which can be used to communicate with/abort a DOM request.

[Methods](#methods "Permalink to Methods")
------------------------------------------

 [`AbortController.abort()`](https://developer.mozilla.org/en-US/docs/Web/API/AbortController/abort)   
Aborts a DOM request before it has completed. This is able to abort [fetch requests](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/fetch), consumption of any response [`Body`](https://developer.mozilla.org/en-US/docs/Web/API/Body), and streams.

[Examples](#examples "Permalink to Examples")
---------------------------------------------

In the following snippet, we aim to download a video using the [Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API).

We first create a controller using the [`AbortController()`](https://developer.mozilla.org/en-US/docs/Web/API/AbortController/AbortController "AbortController()") constructor, then grab a reference to its associated [`AbortSignal`](https://developer.mozilla.org/en-US/docs/Web/API/AbortSignal) object using the [`AbortController.signal`](https://developer.mozilla.org/en-US/docs/Web/API/AbortController/signal) property.

When the [fetch request](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/fetch) is initiated, we pass in the `AbortSignal` as an option inside the request's options object (see `{signal}`, below). This associates the signal and controller with the fetch request and allows us to abort it by calling [`AbortController.abort()`](https://developer.mozilla.org/en-US/docs/Web/API/AbortController/abort), as seen below in the second event listener.

    var controller = new AbortController();
    var signal = controller.signal;

    var downloadBtn = document.querySelector('.download');
    var abortBtn = document.querySelector('.abort');

    downloadBtn.addEventListener('click', fetchVideo);

    abortBtn.addEventListener('click', function() {
      controller.abort();
      console.log('Download aborted');
    });

    function fetchVideo() {
      ...
      fetch(url, {signal}).then(function(response) {
        ...
      }).catch(function(e) {
        reports.textContent = 'Download error: ' + e.message;
      })
    }

**Note**: When `abort()` is called, the `fetch()` promise rejects with a `DOMException` named `AbortError`.

You can find a full working example on GitHub — see <a href="https://github.com/mdn/dom-examples/tree/master/abort-api" class="external">abort-api</a> (<a href="https://mdn.github.io/dom-examples/abort-api/" class="external">see it running live also</a>).

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#interface-abortcontroller">DOM Standard (DOM)<br />
<span class="small"># interface-abortcontroller</span></a></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API)
-   <a href="https://developers.google.com/web/updates/2017/09/abortable-fetch" class="external">Abortable Fetch</a> by Jake Archibald

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/abortcontroller/index.html "Folder: en-us/web/api/abortcontroller (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAbortController%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fabortcontroller%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAbortController%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fabortcontroller%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F03feb1e8a2817f903f18be66fe2efa530f5b88d8%0A*+Document+last+modified%3A+2021-06-04T09%3A32%3A00.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22AbortController%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Jun 4, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/AbortController/contributors.txt)

Change your language Select your preferred language English (US) 한국어 Русский 中文 (简体) 正體中文 (繁體)

Change language

#### Related Topics

1.  **[Document Object Model](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model)**
2.  **[`AbortController`](https://developer.mozilla.org/en-US/docs/Web/API/AbortController)**
3.  Constructor
    1.  [`AbortController()`](https://developer.mozilla.org/en-US/docs/Web/API/AbortController/AbortController)
4.  Properties
    1.  [`signal`](https://developer.mozilla.org/en-US/docs/Web/API/AbortController/signal)
5.  Methods
    1.  [`abort()`](https://developer.mozilla.org/en-US/docs/Web/API/AbortController/abort)
6.  Related pages for DOM
    1.  [`AbortSignal`](https://developer.mozilla.org/en-US/docs/Web/API/AbortSignal)
    2.  [`AbstractRange`](https://developer.mozilla.org/en-US/docs/Web/API/AbstractRange)
    3.  [`Attr`](https://developer.mozilla.org/en-US/docs/Web/API/Attr)
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
