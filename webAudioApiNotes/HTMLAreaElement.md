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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement" class="breadcrumb-current-page"><span data-property="name">HTMLAreaElement</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Properties](#properties)
-   [Methods](#methods)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

HTMLAreaElement
===============

The **`HTMLAreaElement`** interface provides special properties and methods (beyond those of the regular object [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement) interface it also has available to it by inheritance) for manipulating the layout and presentation of [`<area>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/area) elements.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

*Inherits properties from its parent, [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement).*

[`HTMLElement.accessKey`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/accessKey)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) containing a single character that switches input focus to the control.

<span class="page-not-created">`HTMLAreaElement.alt`</span>  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) that reflects the [`alt`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/area#attr-alt) HTML attribute, containing alternative text for the element.

<span class="page-not-created">`HTMLAreaElement.coords`</span>  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) that reflects the [`coords`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/area#attr-coords) HTML attribute, containing coordinates to define the hot-spot region.

<span class="page-not-created">`HTMLAreaElement.download`</span>   
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) indicating that the linked resource is intended to be downloaded rather than displayed in the browser. The value represent the proposed name of the file. If the name is not a valid filename of the underlying OS, browser will adapt it.

[`HTMLAreaElement.hash`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/hash)  
Is a [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString) containing the fragment identifier (including the leading hash mark (\#)), if any, in the referenced URL.

[`HTMLAreaElement.host`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/host)  
Is a [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString) containing the hostname and port (if it's not the default port) in the referenced URL.

[`HTMLAreaElement.hostname`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/hostname)  
Is a [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString) containing the hostname in the referenced URL.

[`HTMLAreaElement.href`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/href)  
Is a [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString) containing that reflects the [`href`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/area#attr-href) HTML attribute, containing a valid URL of a linked resource.

<span class="page-not-created">`HTMLAreaElement.noHref`</span>   
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) flag indicating if the area is inactive (`true`) or active (`false`).

[`HTMLAreaElement.origin`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/origin) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString) containing the origin of the URL, that is its scheme, its domain and its port.

[`HTMLAreaElement.password`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/password)  
Is a [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString) containing the password specified before the domain name.

[`HTMLAreaElement.pathname`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/pathname)  
Is a [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString) containing the path name component, if any, of the referenced URL.

[`HTMLAreaElement.port`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/port)  
Is a [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString) containing the port component, if any, of the referenced URL.

[`HTMLAreaElement.protocol`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/protocol)  
Is a [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString) containing the protocol component (including trailing colon `':'`), of the referenced URL.

[`HTMLAreaElement.referrerPolicy`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/referrerPolicy)   
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) that reflects the [`referrerpolicy`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/area#attr-referrerpolicy) HTML attribute indicating which referrer to use when fetching the linked resource.

[`HTMLAreaElement.rel`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/rel)  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) that reflects the [`rel`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/area#attr-rel) HTML attribute, indicating relationships of the current document to the linked resource.

[`HTMLAreaElement.relList`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/relList) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`DOMTokenList`](https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList) that reflects the [`rel`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/area#attr-rel) HTML attribute, indicating relationships of the current document to the linked resource, as a list of tokens.

[`HTMLAreaElement.search`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/search)  
Is a [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString) containing the search element (including leading question mark `'?'`), if any, of the referenced URL.

<span class="page-not-created">`HTMLAreaElement.shape`</span>  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) that reflects the [`shape`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/area#attr-shape) HTML attribute, indicating the shape of the hot-spot, limited to known values.

[`HTMLOrForeignElement.tabIndex`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOrForeignElement/tabIndex)  
Is a `long` containing the element's position in the tabbing order.

<span class="page-not-created">`HTMLAreaElement.target`</span>  
Is a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) that reflects the [`target`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/area#attr-target) HTML attribute, indicating the browsing context in which to open the linked resource.

[`HTMLAreaElement.username`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/username)  
Is a [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString) containing the username specified before the domain name.

[Methods](#methods "Permalink to Methods")
------------------------------------------

*Inherits methods from its parent, [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement).*

[`HTMLAreaElement.toString()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/toString)  
Returns a [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString) containing the whole URL of the script executed in the [`Worker`](https://developer.mozilla.org/en-US/docs/Web/API/Worker). It is a synonym for [`HTMLAreaElement.href`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/href).

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#htmlareaelement" class="external">HTML Living Standard<br />
<span class="small">The definition of 'HTMLAreaElement' in that specification.</span></a></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   HTML element implementing this interface: [`<area>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/area)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/htmlareaelement/index.html "Folder: en-us/web/api/htmlareaelement (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FHTMLAreaElement%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fhtmlareaelement%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FHTMLAreaElement%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fhtmlareaelement%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fcb20a8045f6cbdbd224b1068e46c8644470dd8c3%0A*+Document+last+modified%3A+2021-06-01T09%3A10%3A31.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22HTMLAreaElement%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Jun 1, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/contributors.txt)

Change your languageSelect your preferred language English (US)日本語Русский中文 (简体)

Change language

#### Related Topics

1.  **[`HTMLAreaElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement)**
2.  Properties
    1.  [`hash`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/hash)
    2.  [`host`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/host)
    3.  [`hostname`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/hostname)
    4.  [`href`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/href)
    5.  [`origin`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/origin)
    6.  [`password`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/password)
    7.  [`pathname`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/pathname)
    8.  [`port`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/port)
    9.  [`protocol`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/protocol)
    10. [`referrerPolicy`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/referrerPolicy)
    11. [`rel`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/rel)
    12. [`relList`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/relList)
    13. [`search`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/search)
    14. [`username`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/username)
3.  Methods
    1.  [`toString()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/toString)
4.  Inheritance:
    1.  [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
    2.  [`Element`](https://developer.mozilla.org/en-US/docs/Web/API/Element)
    3.  [`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node)
    4.  [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)
5.  Related pages for HTML DOM
    1.  [`BeforeUnloadEvent`](https://developer.mozilla.org/en-US/docs/Web/API/BeforeUnloadEvent)
    2.  [`DOMStringMap`](https://developer.mozilla.org/en-US/docs/Web/API/DOMStringMap)
    3.  [`ErrorEvent`](https://developer.mozilla.org/en-US/docs/Web/API/ErrorEvent)
    4.  [`GlobalEventHandlers`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers)
    5.  [`HTMLAnchorElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAnchorElement)
    6.  [`HTMLAudioElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAudioElement)
    7.  [`HTMLBRElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLBRElement)
    8.  [`HTMLBaseElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLBaseElement)
    9.  [`HTMLBaseFontElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLBaseFontElement)
    10. [`HTMLBodyElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLBodyElement)
    11. [`HTMLButtonElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLButtonElement)
    12. [`HTMLCanvasElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement)
    13. [`HTMLContentElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLContentElement)
    14. [`HTMLDListElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDListElement)
    15. [`HTMLDataElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDataElement)
    16. [`HTMLDataListElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDataListElement)
    17. [`HTMLDialogElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDialogElement)
    18. [`HTMLDivElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDivElement)
    19. [`HTMLDocument`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDocument)
    20. [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
    21. [`HTMLEmbedElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLEmbedElement)
    22. [`HTMLFieldSetElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFieldSetElement)
    23. [`HTMLFormControlsCollection`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormControlsCollection)
    24. [`HTMLFormElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement)
    25. [`HTMLFrameSetElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFrameSetElement)
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
