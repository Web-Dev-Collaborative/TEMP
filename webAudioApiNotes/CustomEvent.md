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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/CustomEvent" class="breadcrumb-current-page"><span data-property="name">CustomEvent</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Constructor](#constructor)
-   [Properties](#properties)
-   [Methods](#methods)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [Firing from privileged code to non-privileged code](#firing_from_privileged_code_to_non-privileged_code)
-   [See also](#see_also)

CustomEvent
===========

The **`CustomEvent`** interface represents events initialized by an application for any purpose.

**Note:** This feature is available in [Web Workers](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API)

[Constructor](#constructor "Permalink to Constructor")
------------------------------------------------------

[`CustomEvent()`](https://developer.mozilla.org/en-US/docs/Web/API/CustomEvent/CustomEvent "CustomEvent()")  
Creates a `CustomEvent`.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

[`CustomEvent.detail`](https://developer.mozilla.org/en-US/docs/Web/API/CustomEvent/detail) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Any data passed when initializing the event.

*This interface inherits properties from its parent,* [`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event):

[`Event.bubbles`](https://developer.mozilla.org/en-US/docs/Web/API/Event/bubbles) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
A boolean indicating whether or not the event bubbles up through the DOM.

[`Event.cancelBubble`](https://developer.mozilla.org/en-US/docs/Web/API/Event/cancelBubble)  
A historical alias to [`Event.stopPropagation()`](https://developer.mozilla.org/en-US/docs/Web/API/Event/stopPropagation). Setting its value to `true` before returning from an event handler prevents propagation of the event.

[`Event.cancelable`](https://developer.mozilla.org/en-US/docs/Web/API/Event/cancelable) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
A boolean indicating whether the event is cancelable.

[`Event.composed`](https://developer.mozilla.org/en-US/docs/Web/API/Event/composed) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
A boolean indicating whether or not the event can bubble across the boundary between the shadow DOM and the regular DOM.

[`Event.currentTarget`](https://developer.mozilla.org/en-US/docs/Web/API/Event/currentTarget) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
A reference to the currently registered target for the event. This is the object to which the event is currently slated to be sent. It's possible this has been changed along the way through *retargeting*.

[`Event.deepPath`](https://developer.mozilla.org/en-US/docs/Web/API/Event/composedPath)   
An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of DOM [`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node)s through which the event has bubbled.

[`Event.defaultPrevented`](https://developer.mozilla.org/en-US/docs/Web/API/Event/defaultPrevented) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Indicates whether or not the call to [`event.preventDefault()`](https://developer.mozilla.org/en-US/docs/Web/API/Event/preventDefault) canceled the event.

[`Event.eventPhase`](https://developer.mozilla.org/en-US/docs/Web/API/Event/eventPhase) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Indicates which phase of the event flow is being processed.

[`Event.explicitOriginalTarget`](https://developer.mozilla.org/en-US/docs/Web/API/Event/explicitOriginalTarget) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
The explicit original target of the event (Mozilla-specific.)

[`Event.originalTarget`](https://developer.mozilla.org/en-US/docs/Web/API/Event/originalTarget) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
The original target of the event, before any retargetings. (Mozilla-specific.)

[`Event.returnValue`](https://developer.mozilla.org/en-US/docs/Web/API/Event/returnValue)   
A historical property introduced by Internet Explorer and eventually adopted into the DOM specification in order to ensure existing sites continue to work. Ideally, you should try to use [`Event.preventDefault()`](https://developer.mozilla.org/en-US/docs/Web/API/Event/preventDefault) and [`Event.defaultPrevented`](https://developer.mozilla.org/en-US/docs/Web/API/Event/defaultPrevented) instead, but you can use `returnValue` if you choose to do so.

[`Event.srcElement`](https://developer.mozilla.org/en-US/docs/Web/API/Event/srcElement)   
A non-standard alias (from old versions of Microsoft Internet Explorer) for [`Event.target`](https://developer.mozilla.org/en-US/docs/Web/API/Event/target). Some other browsers are starting to support it for web compatibility purposes.

[`Event.target`](https://developer.mozilla.org/en-US/docs/Web/API/Event/target) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
A reference to the target to which the event was originally dispatched.

[`Event.timeStamp`](https://developer.mozilla.org/en-US/docs/Web/API/Event/timeStamp) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
The time at which the event was created (in milliseconds). By specification, this value is time since epoch—but in reality, browsers' definitions vary. In addition, work is underway to change this to be a [`DOMHighResTimeStamp`](https://developer.mozilla.org/en-US/docs/Web/API/DOMHighResTimeStamp) instead.

[`Event.type`](https://developer.mozilla.org/en-US/docs/Web/API/Event/type) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
The name of the event. Case-insensitive.

[`Event.isTrusted`](https://developer.mozilla.org/en-US/docs/Web/API/Event/isTrusted) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Indicates whether or not the event was initiated by the browser (after a user click, for instance) or by a script (using an event creation method, like [`Event.initEvent`](https://developer.mozilla.org/en-US/docs/Web/API/Event/initEvent)).

### [Deprecated properties](#deprecated_properties "Permalink to Deprecated properties")

[`Event.scoped`](https://developer.mozilla.org/en-US/docs/Web/API/Event/composed) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the given event will bubble across through the shadow root into the standard DOM. Use [`composed`](https://developer.mozilla.org/en-US/docs/Web/API/Event/composed "composed") instead.

[Methods](#methods "Permalink to Methods")
------------------------------------------

[`CustomEvent.initCustomEvent()`](https://developer.mozilla.org/en-US/docs/Web/API/CustomEvent/initCustomEvent)   
Initializes a `CustomEvent` object. If the event has already being dispatched, this method does nothing.

*This interface inherits methods from its parent,* [`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event):

[`Event.composedPath()`](https://developer.mozilla.org/en-US/docs/Web/API/Event/composedPath)  
Returns the event’s path (objects on which listeners will be invoked). This does not include nodes in shadow trees if the shadow root was created with its [`ShadowRoot.mode`](https://developer.mozilla.org/en-US/docs/Web/API/ShadowRoot/mode) closed.

[`Event.preventDefault()`](https://developer.mozilla.org/en-US/docs/Web/API/Event/preventDefault)  
Cancels the event (if it is cancelable).

[`Event.stopImmediatePropagation()`](https://developer.mozilla.org/en-US/docs/Web/API/Event/stopImmediatePropagation)  
For this particular event, prevent all other listeners from being called. This includes listeners attached to the same element as well as those attached to elements that will be traversed later (during the capture phase, for instance).

[`Event.stopPropagation()`](https://developer.mozilla.org/en-US/docs/Web/API/Event/stopPropagation)  
Stops the propagation of events further along in the DOM.

### [Deprecated methods](#deprecated_methods "Permalink to Deprecated methods")

[`Event.initEvent()`](https://developer.mozilla.org/en-US/docs/Web/API/Event/initEvent)   
Initializes the value of an Event created. If the event has already been dispatched, this method does nothing.

<span class="page-not-created">`Event.getPreventDefault()`</span>   
Returns the value of [`Event.defaultPrevented`](https://developer.mozilla.org/en-US/docs/Web/API/Event/defaultPrevented).

<span class="page-not-created">`Event.preventBubble()`</span>   
Prevents the event from bubbling. Use [`event.stopPropagation`](https://developer.mozilla.org/en-US/docs/Web/API/Event/stopPropagation) instead.

<span class="page-not-created">`Event.preventCapture()`</span>   
Prevents the event from bubbling. Use [`event.stopPropagation`](https://developer.mozilla.org/en-US/docs/Web/API/Event/stopPropagation) instead.

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#interface-customevent" class="external">DOM<br />
<span class="small">The definition of 'CustomEvent' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[Firing from privileged code to non-privileged code](#firing_from_privileged_code_to_non-privileged_code "Permalink to Firing from privileged code to non-privileged code")
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------

When firing a `CustomEvent` from privileged code (i.e. an extension) to non-privileged code (i.e. a webpage), security issues should be considered. Firefox and other Gecko applications restrict an object created in one context from being directly used for another, which will automatically prevent security holes, but these restrictions may also prevent your code from running as expected.

While creating a `CustomEvent` object, you must create the object from the same <a href="https://developer.mozilla.org/en-US/docs/XUL/window" class="page-not-created" title="This is a link to an unwritten page">window</a>. The `detail` attribute of your `CustomEvent` will be subjected to the same restrictions. `String` and `Array` values will be readable by the content without restrictions, but custom `Object` will not. While using a custom object, you will need to define the attributes of that object that are readable from the content script using [Components.utils.cloneInto()](https://developer.mozilla.org/en-US/docs/Mozilla/Tech/XPCOM/Language_Bindings/Components.utils.cloneInto).

    // doc is a reference to the content document
    function dispatchCustomEvent(doc) {
      var eventDetail = Components.utils.cloneInto({foo: 'bar'}, doc.defaultView);
      var myEvent = doc.defaultView.CustomEvent("mytype", eventDetail);
      doc.dispatchEvent(myEvent);
    }

But one needs to keep in mind that exposing a function will allow the content script to run it with chrome privileges, which can open a security vulnerability.

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [`Window.postMessage()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/postMessage)
-   <a href="https://developer.mozilla.org/en-US/docs/Code_snippets/Interaction_between_privileged_and_non-privileged_pages" class="page-not-created" title="This is a link to an unwritten page">Interaction between privileged and non-privileged pages</a>
-   [Creating and triggering events](https://developer.mozilla.org/en-US/docs/Web/Events/Creating_and_triggering_events)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/customevent/index.html "Folder: en-us/web/api/customevent (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FCustomEvent%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fcustomevent%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FCustomEvent%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fcustomevent%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fe085698aeab231f6d0c1d3bb7ea6288237946703%0A*+Document+last+modified%3A+2021-05-29T04%3A16%3A39.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22CustomEvent%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 29, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/CustomEvent/contributors.txt)

Change your languageSelect your preferred language English (US)EspañolFrançais日本語한국어中文 (简体)正體中文 (繁體)

Change language

#### Related Topics

1.  **[Document Object Model](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model)**
2.  **[`CustomEvent`](https://developer.mozilla.org/en-US/docs/Web/API/CustomEvent)**
3.  Constructor
    1.  [`CustomEvent()`](https://developer.mozilla.org/en-US/docs/Web/API/CustomEvent/CustomEvent)
4.  Properties
    1.  [`detail`](https://developer.mozilla.org/en-US/docs/Web/API/CustomEvent/detail)
5.  Methods
    1.  [`initCustomEvent()`](https://developer.mozilla.org/en-US/docs/Web/API/CustomEvent/initCustomEvent)
6.  Inheritance:
    1.  [`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event)
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
-   [Terms](https://www.mozilla.org/about/legal/terms/mozilla)
-   [Privacy](https://www.mozilla.org/privacy/websites/)
-   [Cookies](https://www.mozilla.org/privacy/websites/#cookies)
