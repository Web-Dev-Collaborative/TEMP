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
2.  <a href="https://developer.mozilla.org/en-US/docs/Web/API" class="breadcrumb"><span data-property="name">Web APIs</span></a>
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/Event" class="breadcrumb-penultimate"><span data-property="name">Event</span></a>
4.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/Event/target" class="breadcrumb-current-page"><span data-property="name">Event.target</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Syntax](#syntax)
-   [Example](#example)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

Event.target
============

<span class="seoSummary">The `target` property of the [`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event) interface is a reference to the object onto which the event was dispatched. It is different from [`Event.currentTarget`](https://developer.mozilla.org/en-US/docs/Web/API/Event/currentTarget) when the event handler is called during the bubbling or capturing phase of the event.</span>

[Syntax](#syntax "Permalink to Syntax")
---------------------------------------

    const theTarget = someEvent.target;

### [Value](#value "Permalink to Value")

[`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)

[Example](#example "Permalink to Example")
------------------------------------------

The `event.target` property can be used in order to implement **event delegation**.

    // Make a list
    const ul = document.createElement('ul');
    document.body.appendChild(ul);

    const li1 = document.createElement('li');
    const li2 = document.createElement('li');
    ul.appendChild(li1);
    ul.appendChild(li2);

    function hide(evt) {
      // e.target refers to the clicked <li> element
      // This is different than e.currentTarget, which would refer to the parent <ul> in this context
      evt.target.style.visibility = 'hidden';
    }

    // Attach the listener to the list
    // It will fire when each <li> is clicked
    ul.addEventListener('click', hide, false);

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-event-target" class="external">DOM<br />
<span class="small">The definition of 'Event.target' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/dom/#dom-event-target" class="external">DOM4<br />
<span class="small">The definition of 'Event.target' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Events/events.html#Events-Event-target" class="external">Document Object Model (DOM) Level 2 Events Specification<br />
<span class="small">The definition of 'Event.target' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

### [Compatibility notes](#compatibility_notes "Permalink to Compatibility notes")

On IE 6–8, the event model is different. Event listeners are attached with the non-standard [`EventTarget.attachEvent()`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener) method.

In this model, the event object has a [`Event.srcElement`](https://developer.mozilla.org/en-US/docs/Web/API/Event/srcElement) property (instead of the `target` property) and it has the same semantics as `Event.target`.

    function hide(evt) {
      // Support IE6-8
      var target = evt.target || evt.srcElement;
      target.style.visibility = 'hidden';
    }

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Comparison of Event Targets](https://developer.mozilla.org/en-US/docs/Web/API/Event/Comparison_of_Event_Targets)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/event/target/index.html "Folder: en-us/web/api/event/target (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FEvent%2Ftarget%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fevent%2Ftarget%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FEvent%2Ftarget%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fevent%2Ftarget%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F4f1675a38205aeb5f7336aba793ce8e9a1cd1d5d%0A*+Document+last+modified%3A+2021-06-01T10%3A08%3A01.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22Event.target%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Jun 1, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/Event/target/contributors.txt)

Change your languageSelect your preferred language English (US)EspañolFrançais日本語한국어PolskiPortuguês (do Brasil)Русский中文 (简体)正體中文 (繁體)

Change language

#### Related Topics

1.  **[Document Object Model](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model)**
2.  **[`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event)**
3.  Constructor
    1.  [`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event/Event)
4.  Properties
    1.  [`bubbles`](https://developer.mozilla.org/en-US/docs/Web/API/Event/bubbles)
    2.  [`cancelable`](https://developer.mozilla.org/en-US/docs/Web/API/Event/cancelable)
    3.  [`cancelBubble`](https://developer.mozilla.org/en-US/docs/Web/API/Event/cancelBubble)
    4.  [`composed`](https://developer.mozilla.org/en-US/docs/Web/API/Event/composed)
    5.  [`currentTarget`](https://developer.mozilla.org/en-US/docs/Web/API/Event/currentTarget)
    6.  [`defaultPrevented`](https://developer.mozilla.org/en-US/docs/Web/API/Event/defaultPrevented)
    7.  [`eventPhase`](https://developer.mozilla.org/en-US/docs/Web/API/Event/eventPhase)
    8.  [`explicitOriginalTarget`](https://developer.mozilla.org/en-US/docs/Web/API/Event/explicitOriginalTarget)
    9.  [`isTrusted`](https://developer.mozilla.org/en-US/docs/Web/API/Event/isTrusted)
    10. [`originalTarget`](https://developer.mozilla.org/en-US/docs/Web/API/Event/originalTarget)
    11. [`returnValue`](https://developer.mozilla.org/en-US/docs/Web/API/Event/returnValue)
    12. [`srcElement`](https://developer.mozilla.org/en-US/docs/Web/API/Event/srcElement)
    13. *`target`*
    14. [`timeStamp`](https://developer.mozilla.org/en-US/docs/Web/API/Event/timeStamp)
    15. [`type`](https://developer.mozilla.org/en-US/docs/Web/API/Event/type)
5.  Methods
    1.  [`composedPath`](https://developer.mozilla.org/en-US/docs/Web/API/Event/composedPath)
    2.  [`initEvent`](https://developer.mozilla.org/en-US/docs/Web/API/Event/initEvent)
    3.  [`msConvertURL()`](https://developer.mozilla.org/en-US/docs/Web/API/Event/msConvertURL)
    4.  [`preventDefault`](https://developer.mozilla.org/en-US/docs/Web/API/Event/preventDefault)
    5.  [`stopImmediatePropagation`](https://developer.mozilla.org/en-US/docs/Web/API/Event/stopImmediatePropagation)
    6.  [`stopPropagation`](https://developer.mozilla.org/en-US/docs/Web/API/Event/stopPropagation)
6.  Events
    1.  [`bubbles`](https://developer.mozilla.org/en-US/docs/Web/API/Event/bubbles)
    2.  [`cancelable`](https://developer.mozilla.org/en-US/docs/Web/API/Event/cancelable)
    3.  [`cancelBubble`](https://developer.mozilla.org/en-US/docs/Web/API/Event/cancelBubble)
    4.  [`composed`](https://developer.mozilla.org/en-US/docs/Web/API/Event/composed)
    5.  [`composedPath`](https://developer.mozilla.org/en-US/docs/Web/API/Event/composedPath)
    6.  [`currentTarget`](https://developer.mozilla.org/en-US/docs/Web/API/Event/currentTarget)
    7.  [`defaultPrevented`](https://developer.mozilla.org/en-US/docs/Web/API/Event/defaultPrevented)
    8.  [`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event/Event)
    9.  [`eventPhase`](https://developer.mozilla.org/en-US/docs/Web/API/Event/eventPhase)
    10. [`initEvent`](https://developer.mozilla.org/en-US/docs/Web/API/Event/initEvent)
    11. [`isTrusted`](https://developer.mozilla.org/en-US/docs/Web/API/Event/isTrusted)
    12. [`preventDefault`](https://developer.mozilla.org/en-US/docs/Web/API/Event/preventDefault)
    13. [`returnValue`](https://developer.mozilla.org/en-US/docs/Web/API/Event/returnValue)
    14. [`stopImmediatePropagation`](https://developer.mozilla.org/en-US/docs/Web/API/Event/stopImmediatePropagation)
    15. [`stopPropagation`](https://developer.mozilla.org/en-US/docs/Web/API/Event/stopPropagation)
    16. *`target`*
    17. [`timeStamp`](https://developer.mozilla.org/en-US/docs/Web/API/Event/timeStamp)
    18. [`type`](https://developer.mozilla.org/en-US/docs/Web/API/Event/type)
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
    36. [`Element`](https://developer.mozilla.org/en-US/docs/Web/API/Element)
    37. [`ElementTraversal`](https://developer.mozilla.org/en-US/docs/Web/API/ElementTraversal)
    38. [`Entity`](https://developer.mozilla.org/en-US/docs/Web/API/Entity)
    39. [`EntityReference`](https://developer.mozilla.org/en-US/docs/Web/API/EntityReference)
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
