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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLFrameSetElement" class="breadcrumb-current-page"><span data-property="name">HTMLFrameSetElement</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Properties](#properties)
-   [Methods](#methods)
-   [Event handlers](#event_handlers)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

HTMLFrameSetElement
===================

#### Deprecated

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The **`HTMLFrameSetElement`** interface provides special properties (beyond those of the regular [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement) interface they also inherit) for manipulating [`<frameset>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/frameset) elements.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

*Inherits properties from its parent, [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement) and from [`WindowEventHandlers`](https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers).*

<span class="page-not-created">`HTMLFrameSetElement.cols`</span>   
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) structured as a comma-separated list specifying the width of each column inside a frameset.

<span class="page-not-created">`HTMLFrameSetElement.rows`</span>   
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) structured as a comma-separated list specifying the height of each column inside a frameset.

[Methods](#methods "Permalink to Methods")
------------------------------------------

*No specific method; inherits methods from its parent, [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement) and from [`WindowEventHandlers`](https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers).*

[Event handlers](#event_handlers "Permalink to Event handlers")
---------------------------------------------------------------

*No specific event handler; inherits event handlers from its parent, [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement) and from [`WindowEventHandlers`](https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers).*

[`WindowEventHandlers.onafterprint`](https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onafterprint)  
Is an `event handler` representing the code to be called when the `afterprint` event is raised.

[`WindowEventHandlers.onbeforeprint`](https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onbeforeprint)  
Is an `event handler` representing the code to be called when the `beforeprint` event is raised.

[`WindowEventHandlers.onbeforeunload`](https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onbeforeunload)  
Is an `event handler` representing the code to be called when the `beforeunload` event is raised.

[`WindowEventHandlers.onhashchange`](https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onhashchange)  
Is an `event handler` representing the code to be called when the `hashchange` event is raised.

[`WindowEventHandlers.onlanguagechange`](https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onlanguagechange)   
Is an `event handler` representing the code to be called when the `languagechange` event is raised.

[`WindowEventHandlers.onmessage`](https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onmessage)  
Is an `event handler` representing the code to be called when the `message` event is raised.

<span class="page-not-created">`WindowEventHandlers.onoffline`</span>  
Is an `event handler` representing the code to be called when the `offline` event is raised.

<span class="page-not-created">`WindowEventHandlers.ononline`</span>  
Is an `event handler` representing the code to be called when the `online` event is raised.

<span class="page-not-created">`WindowEventHandlers.onpagehide`</span>  
Is an `event handler` representing the code to be called when the `pagehide` event is raised.

<span class="page-not-created">`WindowEventHandlers.onpageshow`</span>  
Is an `event handler` representing the code to be called when the `pageshow` event is raised.

[`WindowEventHandlers.onpopstate`](https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onpopstate)  
Is an `event handler` representing the code to be called when the `popstate` event is raised.

<span class="page-not-created">`WindowEventHandlers.onresize`</span>  
Is an `event handler` representing the code to be called when the `resize` event is raised.

[`WindowEventHandlers.onstorage`](https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onstorage)  
Is an `event handler` representing the code to be called when the `storage` event is raised.

[`WindowEventHandlers.onunload`](https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onunload)  
Is an `event handler` representing the code to be called when the `unload` event is raised.

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#htmlframesetelement" class="external">HTML Living Standard<br />
<span class="small">The definition of 'HTMLFrameSetElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>From the <a href="https://www.w3.org/TR/html52/" class="external" title="The &#39;HTML5&#39; specification">HTML5</a> snapshot, the <a href="https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers"><code>WindowEventHandlers</code></a> interface now have a <code>onlanguagechange</code> property.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/obsolete.html#htmlframesetelement" class="external">HTML5<br />
<span class="small">The definition of 'HTMLFrameSetElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Snapshot of a previous <a href="https://html.spec.whatwg.org/multipage/" class="external" title="The &#39;HTML Living Standard&#39; specification">HTML Living Standard</a><br />
Frames are now obsolete. Implements <a href="https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers"><code>WindowEventHandlers</code></a>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-ID-43829095" class="external">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'HTMLBodyElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/REC-DOM-Level-1/" class="external" title="The &#39;Document Object Model (DOM) Level 1 Specification&#39; specification">Document Object Model (DOM) Level 1 Specification</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-html.html#ID-43829095" class="external">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'HTMLBodyElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   HTML element implementing this interface: [`<frameset>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/frameset)
-   The equivalent of this element outside of frames: [`HTMLBodyElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLBodyElement).

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/htmlframesetelement/index.html "Folder: en-us/web/api/htmlframesetelement (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FHTMLFrameSetElement%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fhtmlframesetelement%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FHTMLFrameSetElement%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fhtmlframesetelement%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fcb20a8045f6cbdbd224b1068e46c8644470dd8c3%0A*+Document+last+modified%3A+2021-06-01T09%3A10%3A31.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22HTMLFrameSetElement%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Jun 1, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFrameSetElement/contributors.txt)

Change your languageSelect your preferred language English (US)Français

Change language

#### Related Topics

1.  **[`HTMLFrameSetElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFrameSetElement)**
2.  Properties
    1.  [`onafterprint`](https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onafterprint)
    2.  [`onbeforeprint`](https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onbeforeprint)
    3.  [`onbeforeunload`](https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onbeforeunload)
    4.  [`onhashchange`](https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onhashchange)
    5.  [`onlanguagechange`](https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onlanguagechange)
    6.  [`onmessage`](https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onmessage)
    7.  [`onmessageerror`](https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onmessageerror)
    8.  [`onpopstate`](https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onpopstate)
    9.  [`onrejectionhandled`](https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onrejectionhandled)
    10. [`onstorage`](https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onstorage)
    11. [`onunhandledrejection`](https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onunhandledrejection)
    12. [`onunload`](https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onunload)
3.  Inheritance:
    1.  [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
    2.  [`Element`](https://developer.mozilla.org/en-US/docs/Web/API/Element)
    3.  [`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node)
    4.  [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)
4.  Related pages for HTML DOM
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
    26. [`HTMLHRElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLHRElement)
    27. [`HTMLHeadElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLHeadElement)
    28. [`HTMLHeadingElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLHeadingElement)
    29. [`HTMLHtmlElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLHtmlElement)
    30. [`HTMLIFrameElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLIFrameElement)
    31. [`HTMLImageElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement)
    32. [`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement)
    33. [`HTMLIsIndexElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLIsIndexElement)
    34. [`HTMLKeygenElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLKeygenElement)
    35. [`HTMLLIElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLLIElement)
    36. [`HTMLLabelElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLLabelElement)
    37. [`HTMLLegendElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLLegendElement)
    38. [`HTMLLinkElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLLinkElement)
    39. [`HTMLMapElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMapElement)
    40. [`HTMLMediaElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement)
    41. [`HTMLMetaElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMetaElement)
    42. [`HTMLMeterElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMeterElement)
    43. [`HTMLModElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLModElement)
    44. [`HTMLOListElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOListElement)
    45. [`HTMLObjectElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLObjectElement)
    46. [`HTMLOptGroupElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOptGroupElement)
    47. [`HTMLOptionElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOptionElement)
    48. [`HTMLOptionsCollection`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOptionsCollection)
    49. [`HTMLOutputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOutputElement)
    50. [`HTMLParagraphElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLParagraphElement)
    51. [`HTMLParamElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLParamElement)
    52. [`HTMLPictureElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLPictureElement)
    53. [`HTMLPreElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLPreElement)
    54. [`HTMLProgressElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLProgressElement)
    55. [`HTMLQuoteElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLQuoteElement)
    56. [`HTMLScriptElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLScriptElement)
    57. [`HTMLSelectElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement)
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