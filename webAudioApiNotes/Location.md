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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/Location" class="breadcrumb-current-page"><span data-property="name">Location</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Anatomy Of Location](#anatomy_of_location)
-   [Properties](#properties)
-   [Methods](#methods)
-   [Examples](#examples)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

Location
========

The **`Location`** interface represents the location (URL) of the object it is linked to. Changes done on it are reflected on the object it relates to. Both the [`Document`](https://developer.mozilla.org/en-US/docs/Web/API/Document) and [`Window`](https://developer.mozilla.org/en-US/docs/Web/API/Window) interface have such a linked `Location`, accessible via [`Document.location`](https://developer.mozilla.org/en-US/docs/Web/API/Document/location) and [`Window.location`](https://developer.mozilla.org/en-US/docs/Web/API/Window/location) respectively.

[Anatomy Of Location](#anatomy_of_location "Permalink to Anatomy Of Location")
------------------------------------------------------------------------------

### [HTML](#html "Permalink to HTML")

    <span id="href"><span id="origin"><span id="protocol">http:</span>//<span id="host"><span id="hostname">example.org</span>:<span id="port">8888</span></span></span><span id="pathname">/foo/bar</span><span id="search">?q=baz</span><span id="hash">#bang</span></span>

### [CSS](#css "Permalink to CSS")

    html, body {height:100%;}
    html {display:table; width:100%;}
    body {display:table-cell; text-align:center; vertical-align:middle; font-family:georgia; font-size:230%; line-height:1em; white-space:nowrap;}

    [title] {position:relative; display:inline-block; box-sizing:border-box; /*border-bottom:.5em solid;*/ line-height:2em; cursor:pointer;}

    [title]:before {content:attr(title); font-family:monospace; position:absolute; top:100%; width:100%; left:50%; margin-left:-50%; font-size:40%; line-height:1.5; background:black;}
    [title]:hover:before,
    :target:before {background:black; color:yellow;}

    [title] [title]:before {margin-top:1.5em;}
    [title] [title] [title]:before {margin-top:3em;}
    [title] [title] [title] [title]:before {margin-top:4.5em;}

    [title]:hover,
    :target {position:relative; z-index:1; outline:50em solid rgba(255,255,255,.8);}

### [JavaScript](#javascript "Permalink to JavaScript")

    [].forEach.call(document.querySelectorAll('[title][id]'), function (node) {
      node.addEventListener("click", function(e) {
        e.preventDefault();
        e.stopPropagation();
        window.location.hash = '#' + e.target.getAttribute('id');
      });
    });
    [].forEach.call(document.querySelectorAll('[title]:not([id])'), function (node) {
      node.addEventListener("click", function(e) {
        e.preventDefault();
        e.stopPropagation();
        window.location.hash = '';
      });
    });

### [Result](#result "Permalink to Result")

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

[`Location.ancestorOrigins`](https://developer.mozilla.org/en-US/docs/Web/API/Location/ancestorOrigins)  
Is a static [`DOMStringList`](https://developer.mozilla.org/en-US/docs/Web/API/DOMStringList) containing, in reverse order, the origins of all ancestor browsing contexts of the document associated with the given `Location` object.

[`Location.href`](https://developer.mozilla.org/en-US/docs/Web/API/Location/href)  
Is a stringifier that returns a [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString) containing the entire URL. If changed, the associated document navigates to the new page. It can be set from a different origin than the associated document.

[`Location.protocol`](https://developer.mozilla.org/en-US/docs/Web/API/Location/protocol)  
Is a [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString) containing the protocol scheme of the URL, including the final `':'`.

[`Location.host`](https://developer.mozilla.org/en-US/docs/Web/API/Location/host)  
Is a [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString) containing the host, that is the *hostname*, a `':'`, and the *port* of the URL.

[`Location.hostname`](https://developer.mozilla.org/en-US/docs/Web/API/Location/hostname)  
Is a [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString) containing the domain of the URL.

[`Location.port`](https://developer.mozilla.org/en-US/docs/Web/API/Location/port)  
Is a [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString) containing the port number of the URL.

[`Location.pathname`](https://developer.mozilla.org/en-US/docs/Web/API/Location/pathname)  
Is a [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString) containing an initial `'/'` followed by the path of the URL, not including the query string or fragment.

[`Location.search`](https://developer.mozilla.org/en-US/docs/Web/API/Location/search)  
Is a [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString) containing a `'?'` followed by the parameters or "querystring" of the URL. Modern browsers provide [URLSearchParams](https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/get#example) and [URL.searchParams](https://developer.mozilla.org/en-US/docs/Web/API/URL/searchParams#example) to make it easy to parse out the parameters from the querystring.

[`Location.hash`](https://developer.mozilla.org/en-US/docs/Web/API/Location/hash)  
Is a [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString) containing a `'#'` followed by the fragment identifier of the URL.

[`Location.origin`](https://developer.mozilla.org/en-US/docs/Web/API/Location/origin) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString) containing the canonical form of the origin of the specific location.

[Methods](#methods "Permalink to Methods")
------------------------------------------

[`Location.assign()`](https://developer.mozilla.org/en-US/docs/Web/API/Location/assign)  
Loads the resource at the URL provided in parameter.

[`Location.reload()`](https://developer.mozilla.org/en-US/docs/Web/API/Location/reload)  
Reloads the current URL, like the Refresh button.

[`Location.replace()`](https://developer.mozilla.org/en-US/docs/Web/API/Location/replace)  
Replaces the current resource with the one at the provided URL (redirects to the provided URL). The difference from the `assign()` method and setting the `href` property is that after using `replace()` the current page will not be saved in session [`History`](https://developer.mozilla.org/en-US/docs/Web/API/History), meaning the user won't be able to use the *back* button to navigate to it.

[`Location.toString()`](https://developer.mozilla.org/en-US/docs/Web/API/Location/toString)  
Returns a [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString) containing the whole URL. It is a synonym for [`HTMLAnchorElement.href`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAnchorElement/href), though it can't be used to modify the value.

[Examples](#examples "Permalink to Examples")
---------------------------------------------

    // Create anchor element and use href property for the purpose of this example
    // A more correct alternative is to browse to the URL and use document.location or window.location
    var url = document.createElement('a');
    url.href = 'https://developer.mozilla.org:8080/en-US/search?q=URL#search-results-close-container';
    console.log(url.href);      // https://developer.mozilla.org:8080/en-US/search?q=URL#search-results-close-container
    console.log(url.protocol);  // https:
    console.log(url.host);      // developer.mozilla.org:8080
    console.log(url.hostname);  // developer.mozilla.org
    console.log(url.port);      // 8080
    console.log(url.pathname);  // /en-US/search
    console.log(url.search);    // ?q=URL
    console.log(url.hash);      // #search-results-close-container
    console.log(url.origin);    // https://developer.mozilla.org:8080

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/browsers.html#the-location-interface" class="external">HTML Living Standard<br />
<span class="small">The definition of 'Location' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   Two methods creating such an object: [`Window.location`](https://developer.mozilla.org/en-US/docs/Web/API/Window/location) and [`Document.location`](https://developer.mozilla.org/en-US/docs/Web/API/Document/location).
-   URL related interfaces: [`URL`](https://developer.mozilla.org/en-US/docs/Web/API/URL), [`URLSearchParams`](https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams) and <span class="page-not-created">`HTMLHyperlinkElementUtils`</span>

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/location/index.html "Folder: en-us/web/api/location (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FLocation%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Flocation%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FLocation%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Flocation%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fb06b69b145b54e5a4d7240a3363b345c42b3294e%0A*+Document+last+modified%3A+2021-05-31T16%3A54%3A27.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22Location%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/Location/contributors.txt)

Change your languageSelect your preferred language English (US)EspañolFrançais日本語한국어PolskiPortuguês (do Brasil)Русский中文 (简体)

Change language

#### Related Topics

1.  **[`Location`](https://developer.mozilla.org/en-US/docs/Web/API/Location)**
2.  Properties
    1.  [`Location: ancestorOrigins`](https://developer.mozilla.org/en-US/docs/Web/API/Location/ancestorOrigins)
    2.  [`Location: hash`](https://developer.mozilla.org/en-US/docs/Web/API/Location/hash)
    3.  [`Location: host`](https://developer.mozilla.org/en-US/docs/Web/API/Location/host)
    4.  [`Location: hostname`](https://developer.mozilla.org/en-US/docs/Web/API/Location/hostname)
    5.  [`Location: href`](https://developer.mozilla.org/en-US/docs/Web/API/Location/href)
    6.  [`Location: origin`](https://developer.mozilla.org/en-US/docs/Web/API/Location/origin)
    7.  [`Location: password`](https://developer.mozilla.org/en-US/docs/Web/API/Location/password)
    8.  [`Location: pathname`](https://developer.mozilla.org/en-US/docs/Web/API/Location/pathname)
    9.  [`Location: port`](https://developer.mozilla.org/en-US/docs/Web/API/Location/port)
    10. [`Location: protocol`](https://developer.mozilla.org/en-US/docs/Web/API/Location/protocol)
    11. [`Location: search`](https://developer.mozilla.org/en-US/docs/Web/API/Location/search)
    12. [`Location: username`](https://developer.mozilla.org/en-US/docs/Web/API/Location/username)
3.  Methods
    1.  [`Location: assign()`](https://developer.mozilla.org/en-US/docs/Web/API/Location/assign)
    2.  [`Location: reload()`](https://developer.mozilla.org/en-US/docs/Web/API/Location/reload)
    3.  [`Location: replace()`](https://developer.mozilla.org/en-US/docs/Web/API/Location/replace)
    4.  [`Location: toString()`](https://developer.mozilla.org/en-US/docs/Web/API/Location/toString)
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
    26. [`HTMLFrameSetElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFrameSetElement)
    27. [`HTMLHRElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLHRElement)
    28. [`HTMLHeadElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLHeadElement)
    29. [`HTMLHeadingElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLHeadingElement)
    30. [`HTMLHtmlElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLHtmlElement)
    31. [`HTMLIFrameElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLIFrameElement)
    32. [`HTMLImageElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement)
    33. [`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement)
    34. [`HTMLIsIndexElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLIsIndexElement)
    35. [`HTMLKeygenElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLKeygenElement)
    36. [`HTMLLIElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLLIElement)
    37. [`HTMLLabelElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLLabelElement)
    38. [`HTMLLegendElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLLegendElement)
    39. [`HTMLLinkElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLLinkElement)
    40. [`HTMLMapElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMapElement)
    41. [`HTMLMediaElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement)
    42. [`HTMLMetaElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMetaElement)
    43. [`HTMLMeterElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMeterElement)
    44. [`HTMLModElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLModElement)
    45. [`HTMLOListElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOListElement)
    46. [`HTMLObjectElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLObjectElement)
    47. [`HTMLOptGroupElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOptGroupElement)
    48. [`HTMLOptionElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOptionElement)
    49. [`HTMLOptionsCollection`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOptionsCollection)
    50. [`HTMLOutputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOutputElement)
    51. [`HTMLParagraphElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLParagraphElement)
    52. [`HTMLParamElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLParamElement)
    53. [`HTMLPictureElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLPictureElement)
    54. [`HTMLPreElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLPreElement)
    55. [`HTMLProgressElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLProgressElement)
    56. [`HTMLQuoteElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLQuoteElement)
    57. [`HTMLScriptElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLScriptElement)
    58. [`HTMLSelectElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement)
    59. [`HTMLShadowElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLShadowElement)
    60. [`HTMLSourceElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSourceElement)
    61. [`HTMLSpanElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSpanElement)
    62. [`HTMLStyleElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLStyleElement)
    63. [`HTMLTableCaptionElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableCaptionElement)
    64. [`HTMLTableCellElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableCellElement)
    65. [`HTMLTableColElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableColElement)
    66. [`HTMLTableDataCellElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableDataCellElement)
    67. [`HTMLTableElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableElement)
    68. [`HTMLTableHeaderCellElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableHeaderCellElement)
    69. [`HTMLTableRowElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableRowElement)
    70. [`HTMLTableSectionElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableSectionElement)
    71. [`HTMLTemplateElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTemplateElement)
    72. [`HTMLTextAreaElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTextAreaElement)
    73. [`HTMLTimeElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTimeElement)
    74. [`HTMLTitleElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTitleElement)
    75. [`HTMLTrackElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTrackElement)
    76. [`HTMLUListElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLUListElement)
    77. [`HTMLUnknownElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLUnknownElement)
    78. [`HTMLVideoElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLVideoElement)
    79. [`HashChangeEvent`](https://developer.mozilla.org/en-US/docs/Web/API/HashChangeEvent)
    80. [`History`](https://developer.mozilla.org/en-US/docs/Web/API/History)
    81. [`ImageData`](https://developer.mozilla.org/en-US/docs/Web/API/ImageData)
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
