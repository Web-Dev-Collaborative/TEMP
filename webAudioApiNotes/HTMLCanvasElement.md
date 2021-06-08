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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement" class="breadcrumb-current-page"><span data-property="name">HTMLCanvasElement</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Properties](#properties)
-   [Methods](#methods)
-   [Events](#events)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

HTMLCanvasElement
=================

The **`HTMLCanvasElement`** interface provides properties and methods for manipulating the layout and presentation of [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) elements. The `HTMLCanvasElement` interface also inherits the properties and methods of the [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement) interface.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

*Inherits properties from its parent, [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement).*

[`HTMLCanvasElement.height`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/height)  
The [`height`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas#attr-height) HTML attribute of the [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element is a positive `integer` reflecting the number of logical pixels (or RGBA values) going down one column of the canvas. When the attribute is not specified, or if it is set to an invalid value, like a negative, the default value of `150` is used. If no \[separate\] CSS height is assigned to the [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas), then this value will also be used as the height of the canvas in the length-unit CSS Pixel.

[`HTMLCanvasElement.width`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/width)  
The [`width`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas#attr-width) HTML attribute of the [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element is a positive `integer` reflecting the number of logical pixels (or RGBA values) going across one row of the canvas. When the attribute is not specified, or if it is set to an invalid value, like a negative, the default value of `300` is used. If no \[separate\] CSS width is assigned to the [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas), then this value will also be used as the width of the canvas in the length-unit CSS Pixel.

[`HTMLCanvasElement.mozOpaque`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/mozOpaque)   
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) reflecting the [`moz-opaque`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas#attr-moz-opaque) HTML attribute of the [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element. It lets the canvas know whether or not translucency will be a factor. If the canvas knows there's no translucency, painting performance can be optimized. This is only supported in Mozilla-based browsers; use the standardized [`canvas.getContext('2d', { alpha: false })`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/getContext "canvas.getContext('2d', { alpha: false })") instead.

<span class="page-not-created">`HTMLCanvasElement.mozPrintCallback`</span>   
Is a `function` that is Initially null. Web content can set this to a JavaScript function that will be called when the canvas is to be redrawn while the page is being printed. When called, the callback is passed a "printState" object that implements the <a href="https://searchfox.org/mozilla-central/search?q=interface%20MozCanvasPrintState&amp;path=HTMLCanvasElement.webidl" class="external">MozCanvasPrintState</a> interface. The callback can get the context to draw to from the printState object and must then call done() on it when finished. The purpose of `mozPrintCallback` is to obtain a higher resolution rendering of the canvas at the resolution of the printer being used. <a href="https://blog.mozilla.org/labs/2012/09/a-new-way-to-control-printing-output/" class="external">See this blog post.</a>

[Methods](#methods "Permalink to Methods")
------------------------------------------

*Inherits methods from its parent, [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement).*

[`HTMLCanvasElement.captureStream()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/captureStream)   
Returns a [`CanvasCaptureMediaStreamTrack`](https://developer.mozilla.org/en-US/docs/Web/API/CanvasCaptureMediaStreamTrack) that is a real-time video capture of the surface of the canvas.

[`HTMLCanvasElement.getContext()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/getContext)  
Returns a drawing context on the canvas, or null if the context ID is not supported. A drawing context lets you draw on the canvas. Calling getContext with `"2d"` returns a [`CanvasRenderingContext2D`](https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D) object, whereas calling it with `"webgl"` (or `"experimental-webgl"`) returns a [`WebGLRenderingContext`](https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext) object. This context is only available on browsers that implement [WebGL](https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API).

[`HTMLCanvasElement.toDataURL()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/toDataURL)  
Returns a data-URL containing a representation of the image in the format specified by the `type` parameter (defaults to `png`). The returned image is in a resolution of 96dpi.

[`HTMLCanvasElement.toBlob()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/toBlob)  
Creates a [`Blob`](https://developer.mozilla.org/en-US/docs/Web/API/Blob) object representing the image contained in the canvas; this file may be cached on the disk or stored in memory at the discretion of the user agent.

[`HTMLCanvasElement.transferControlToOffscreen()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/transferControlToOffscreen)   
Transfers control to an [`OffscreenCanvas`](https://developer.mozilla.org/en-US/docs/Web/API/OffscreenCanvas) object, either on the main thread or on a worker.

### [Obsolete methods](#obsolete_methods "Permalink to Obsolete methods")

[`HTMLCanvasElement.mozGetAsFile()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/mozGetAsFile)   
Returns a [`File`](https://developer.mozilla.org/en-US/docs/Web/API/File) object representing the image contained in the canvas; this file is a memory-based file, with the specified `name`. If `type` is not specified, the image type is `image/png`.

[Events](#events "Permalink to Events")
---------------------------------------

Listen to these events using `addEventListener()`.

`webglcontextcreationerror`  
Fired if the user agent is unable to create a `WebGLRenderingContext` or `WebGL2RenderingContext` context.

`webglcontextlost`  
Fired if the user agent detects that the drawing buffer associated with a `WebGLRenderingContext` or `WebGL2RenderingContext` object has been lost.

`webglcontextrestored`  
Fired if the user agent restores the drawing buffer for a `WebGLRenderingContext` or `WebGL2RenderingContext` object.

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#htmlcanvaselement" class="external">HTML Living Standard<br />
<span class="small">The definition of 'HTMLCanvasElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Primary definition of <code>HTMLCanvasElement</code>.</td></tr><tr class="even"><td><a href="https://w3c.github.io/mediacapture-fromelement/#html-canvas-element-media-capture-extensions" class="external">Media Capture from DOM Elements<br />
<span class="small">The definition of 'HTMLCanvasElement' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds the method <code>captureStream()</code>.</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   HTML element implementing this interface: [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/htmlcanvaselement/index.html "Folder: en-us/web/api/htmlcanvaselement (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FHTMLCanvasElement%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fhtmlcanvaselement%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FHTMLCanvasElement%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fhtmlcanvaselement%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fcb20a8045f6cbdbd224b1068e46c8644470dd8c3%0A*+Document+last+modified%3A+2021-06-01T09%3A10%3A31.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22HTMLCanvasElement%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Jun 1, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/contributors.txt)

Change your languageSelect your preferred language English (US)DeutschEspañolFrançais日本語한국어PolskiPortuguês (do Brasil)Русский中文 (简体)正體中文 (繁體)

Change language

#### Related Topics

1.  **[Canvas API](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API)**
2.  **[`HTMLCanvasElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement)**
3.  Properties
    1.  [`height`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/height)
    2.  [`mozOpaque`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/mozOpaque)
    3.  [`width`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/width)
4.  Methods
    1.  [`captureStream()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/captureStream)
    2.  [`getContext()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/getContext)
    3.  [`mozFetchAsStream()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/mozFetchAsStream)
    4.  [`mozGetAsFile()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/mozGetAsFile)
    5.  [`toBlob()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/toBlob)
    6.  [`toDataURL()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/toDataURL)
    7.  [`transferControlToOffscreen()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/transferControlToOffscreen)
5.  Events
    1.  [`webglcontextlost`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/webglcontextlost_event)
6.  Inheritance:
    1.  [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
    2.  [`Element`](https://developer.mozilla.org/en-US/docs/Web/API/Element)
    3.  [`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node)
    4.  [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)
7.  Related pages for Canvas API
    1.  [`Canvas`](https://developer.mozilla.org/en-US/docs/Web/API/Canvas)
    2.  [`CanvasGradient`](https://developer.mozilla.org/en-US/docs/Web/API/CanvasGradient)
    3.  [`CanvasImageSource`](https://developer.mozilla.org/en-US/docs/Web/API/CanvasImageSource)
    4.  [`CanvasPattern`](https://developer.mozilla.org/en-US/docs/Web/API/CanvasPattern)
    5.  [`CanvasRenderingContext2D`](https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D)
    6.  [`ImageBitmap`](https://developer.mozilla.org/en-US/docs/Web/API/ImageBitmap)
    7.  [`ImageBitmapFactories`](https://developer.mozilla.org/en-US/docs/Web/API/ImageBitmapFactories)
    8.  [`ImageBitmapRenderingContext`](https://developer.mozilla.org/en-US/docs/Web/API/ImageBitmapRenderingContext)
    9.  [`ImageData`](https://developer.mozilla.org/en-US/docs/Web/API/ImageData)
    10. [`OffscreenCanvas`](https://developer.mozilla.org/en-US/docs/Web/API/OffscreenCanvas)
    11. [`Path2D`](https://developer.mozilla.org/en-US/docs/Web/API/Path2D)
    12. [`RenderingContext`](https://developer.mozilla.org/en-US/docs/Web/API/RenderingContext)
    13. [`TextMetrics`](https://developer.mozilla.org/en-US/docs/Web/API/TextMetrics)

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
