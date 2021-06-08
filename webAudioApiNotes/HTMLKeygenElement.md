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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLKeygenElement" class="breadcrumb-current-page"><span data-property="name">HTMLKeygenElement</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Properties](#properties)
-   [Methods](#methods)
-   [Browser compatibility](#browser_compatibility)

HTMLKeygenElement
=================

#### Deprecated

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Note:** This page describes the Keygen Element interface as specified, not as currently implemented by Gecko. See <a href="https://bugzilla.mozilla.org/show_bug.cgi?id=101019" class="external">bug 101019</a> for details and status.

The [`<keygen>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/keygen) elements expose the **`HTMLKeygenElement`** interface, which provides special properties and methods (beyond the regular [`element`](https://developer.mozilla.org/en-US/docs/Web/API/Element) object interface they also have available to them by inheritance) for manipulating the layout and presentation of `keygen` elements.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

autofocus  
Is a `Boolean` that reflects the [`autofocus`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/keygen#attr-autofocus) HTML attribute, indicating that the form control should have input focus when the page loads.

challenge  
Is a `DOMString` that reflects the [`challenge`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/keygen#attr-challenge) HTML attribute, containing a challenge string that is packaged with the submitted key.

form <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Is a `HTMLFormElement` that indicates the control's form owner, reflecting the [`form`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/keygen#attr-form) HTML attribute if it is defined.

keytype  
Is a `DOMString` that reflects the [`keytype`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/keygen#attr-keytype) HTML attribute, containing the type of key used.

labels <span class="badge inline readonly" title="This value may not be changed.">Read only </span> <span class="notecard inline warning">Unimplemented (see <a href="https://bugzilla.mozilla.org/show_bug.cgi?id=556743" class="external">bug 556743</a>)</span>  
Is a `NodeList` that represents a list of label elements associated with this keygen element.

name  
Is a `DOMString` that reflects the [`name`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/keygen#attr-name) HTML attribute, containing the name for the control that is submitted with form data.

type <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Is a `DOMString` that must be the value `keygen`.

validationMessage <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Is a `DOMString` representing a localized message that describes the validation constraints that the control does not satisfy (if any). This is the empty string if the control is not a candidate for constraint validation (`willValidate` is false), or it satisfies its constraints.

validity <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Is a `ValidityState` representing the validity states that this element is in.

willValidate  
Is a `Boolean` that is always false because `keygen` objects are never candidates for constraint validation.

[Methods](#methods "Permalink to Methods")
------------------------------------------

<table><thead><tr class="header"><th>Name &amp; Arguments</th><th>Return</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>checkValidity()</code></td><td><code>Boolean</code></td><td>Always returns true because <code>keygen</code> objects are never candidates for constraint validation.</td></tr><tr class="even"><td><code>setCustomValidity(in DOMString error)</code></td><td><code>void</code></td><td>Sets a custom validity message for the element. If this message is not the empty string, then the element is suffering from a custom validity error, and does not validate.</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/htmlkeygenelement/index.html "Folder: en-us/web/api/htmlkeygenelement (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FHTMLKeygenElement%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fhtmlkeygenelement%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FHTMLKeygenElement%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fhtmlkeygenelement%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fcb20a8045f6cbdbd224b1068e46c8644470dd8c3%0A*+Document+last+modified%3A+2021-06-01T09%3A10%3A31.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22HTMLKeygenElement%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Jun 1, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/HTMLKeygenElement/contributors.txt)

Change your languageSelect your preferred language English (US)日本語

Change language

#### Related Topics

1.  **[`HTMLKeygenElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLKeygenElement)**
2.  Related pages for HTML DOM
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
    26. [`HTMLFrameSetElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFrameSetElement)
    27. [`HTMLHRElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLHRElement)
    28. [`HTMLHeadElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLHeadElement)
    29. [`HTMLHeadingElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLHeadingElement)
    30. [`HTMLHtmlElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLHtmlElement)
    31. [`HTMLIFrameElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLIFrameElement)
    32. [`HTMLImageElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement)
    33. [`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement)
    34. [`HTMLIsIndexElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLIsIndexElement)
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
