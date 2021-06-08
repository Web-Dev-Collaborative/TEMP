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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API" class="breadcrumb-penultimate"><span data-property="name">Web Workers API</span></a>
4.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Structured_clone_algorithm" class="breadcrumb-current-page"><span data-property="name">The structured clone algorithm</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Things that don't work with structured clone](#things_that_dont_work_with_structured_clone)
-   [Supported types](#supported_types)
-   [See also](#see_also)

The structured clone algorithm
==============================

<span class="seoSummary">The **structured clone algorithm** copies complex JavaScript objects. It is used internally to transfer data between [Workers](https://developer.mozilla.org/en-US/docs/Web/API/Worker) via [`postMessage()`](https://developer.mozilla.org/en-US/docs/Web/API/Worker/postMessage "postMessage()"), storing objects with [IndexedDB](https://developer.mozilla.org/en-US/docs/Glossary/IndexedDB), or copying objects for [other APIs](#see_also).</span> It clones by recursing through the input object while maintaining a map of previously visited references, to avoid infinitely traversing cycles.

[Things that don't work with structured clone](#things_that_dont_work_with_structured_clone "Permalink to Things that don't work with structured clone")
--------------------------------------------------------------------------------------------------------------------------------------------------------

-   [`Function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function) objects cannot be duplicated by the structured clone algorithm; attempting to throws a `DATA_CLONE_ERR` exception.
-   Cloning DOM nodes likewise throws a `DATA_CLONE_ERR` exception.
-   Certain object properties are not preserved:
    -   The `lastIndex` property of [`RegExp`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp) objects is not preserved.
    -   Property descriptors, setters, getters, and similar metadata-like features are not duplicated. For example, if an object is marked readonly with a [property descriptor](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/getOwnPropertyDescriptor), it will be read/write in the duplicate, since that's the default.
    -   The prototype chain is not walked or duplicated.

**Note**: Native [`Error`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Error) types can be cloned in Chrome, and Firefox is <a href="https://bugzilla.mozilla.org/show_bug.cgi?id=1556604" class="external">working on it</a>.

[Supported types](#supported_types "Permalink to Supported types")
------------------------------------------------------------------

<table><thead><tr class="header"><th>Object type</th><th>Notes</th></tr></thead><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#primitive_values">All primitive types</a></td><td>However, not symbols.</td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean">Boolean</a> objects</td><td></td></tr><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/String">String</a> objects</td><td></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date">Date</a></td><td></td></tr><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp">RegExp</a></td><td><code>lastIndex</code> is not preserved.</td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/Blob"><code>Blob</code></a></td><td></td></tr><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/File"><code>File</code></a></td><td></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/FileList"><code>FileList</code></a></td><td></td></tr><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer">ArrayBuffer</a></td><td></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/ArrayBufferView">ArrayBufferView</a></td><td>Including other <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Typed_arrays">typed arrays</a>.</td></tr><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/ImageBitmap"><code>ImageBitmap</code></a></td><td></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/ImageData"><code>ImageData</code></a></td><td></td></tr><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array">Array</a></td><td></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object">Object</a></td><td><strong>Only</strong> plain objects (e.g. from object literals)</td></tr><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map">Map</a></td><td></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set">Set</a></td><td></td></tr></tbody></table>

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   <a href="https://www.w3.org/TR/html5/infrastructure.html#safe-passing-of-structured-data" class="external">HTML Specification: Safe passing of structured data</a>
-   [`window.history`](https://developer.mozilla.org/en-US/docs/Web/API/Window/history)
-   [`window.postMessage()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/postMessage)
-   [Web Workers](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API)
-   [IndexedDB](https://developer.mozilla.org/en-US/docs/Web/API/IndexedDB_API)
-   <a href="https://developer.mozilla.org/en-US/docs/Components.utils.cloneInto" class="page-not-created" title="This is a link to an unwritten page">Components.utils.cloneInto</a>

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/web_workers_api/structured_clone_algorithm/index.html "Folder: en-us/web/api/web_workers_api/structured_clone_algorithm (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWeb_Workers_API%2FStructured_clone_algorithm%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fweb_workers_api%2Fstructured_clone_algorithm%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWeb_Workers_API%2FStructured_clone_algorithm%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fweb_workers_api%2Fstructured_clone_algorithm%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fe29fc9eb9f6e1e9eeb881ba8d7ea387f469c8856%0A*+Document+last+modified%3A+2021-01-20T02%3A04%3A45.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22The+structured+clone+algorithm%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Jan 20, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Structured_clone_algorithm/contributors.txt)

Change your languageSelect your preferred language English (US)Français日本語한국어Русский中文 (简体)

Change language

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

#### Mozilla

-   <a href="https://twitter.com/mozilla" class="social-icon twitter"><span class="visually-hidden">Mozilla on Twitter</span></a>
-   <a href="https://www.instagram.com/mozillagram/" class="social-icon instagram"><span class="visually-hidden">Mozilla on Instagram</span></a>

© 2005-2021 Mozilla and individual contributors. Content is available under [these licenses](https://developer.mozilla.org/docs/MDN/About#Copyrights_and_licenses).

-   [Terms](https://www.mozilla.org/about/legal/terms/mozilla)
-   [Privacy](https://www.mozilla.org/privacy/websites/)
-   [Cookies](https://www.mozilla.org/privacy/websites/#cookies)
