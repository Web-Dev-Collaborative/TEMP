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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/ImageData" class="breadcrumb-current-page"><span data-property="name">ImageData</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Constructors](#constructors)
-   [Properties](#properties)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

ImageData
=========

<span class="seoSummary">The `ImageData` interface represents the underlying pixel data of an area of a [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element.</span> It is created using the [`ImageData()`](https://developer.mozilla.org/en-US/docs/Web/API/ImageData/ImageData "ImageData()") constructor or creator methods on the [`CanvasRenderingContext2D`](https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D) object associated with a canvas: [`createImageData()`](https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/createImageData "createImageData()") and [`getImageData()`](https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/getImageData "getImageData()"). It can also be used to set a part of the canvas by using [`putImageData()`](https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/putImageData "putImageData()").

**Note:** This feature is available in [Web Workers](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API)

[Constructors](#constructors "Permalink to Constructors")
---------------------------------------------------------

[`ImageData()`](https://developer.mozilla.org/en-US/docs/Web/API/ImageData/ImageData "ImageData()")   
Creates an `ImageData` object from a given [`Uint8ClampedArray`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint8ClampedArray) and the size of the image it contains. If no array is given, it creates an image of a transparent black rectangle. Note that this is the most common way to create such an object in workers as [`createImageData()`](https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/createImageData "createImageData()") is not available there.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

[`ImageData.data`](https://developer.mozilla.org/en-US/docs/Web/API/ImageData/data) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Is a [`Uint8ClampedArray`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint8ClampedArray) representing a one-dimensional array containing the data in the RGBA order, with integer values between `0` and `255` (inclusive).

[`ImageData.height`](https://developer.mozilla.org/en-US/docs/Web/API/ImageData/height) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Is an `unsigned long` representing the actual height, in pixels, of the `ImageData`.

[`ImageData.width`](https://developer.mozilla.org/en-US/docs/Web/API/ImageData/width) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Is an `unsigned long` representing the actual width, in pixels, of the `ImageData`.

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/canvas.html#imagedata" class="external">HTML Living Standard<br />
<span class="small">The definition of 'ImageData' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [`CanvasRenderingContext2D`](https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D)
-   The [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element and its associated interface, [`HTMLCanvasElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement).

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/imagedata/index.html "Folder: en-us/web/api/imagedata (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FImageData%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fimagedata%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FImageData%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fimagedata%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fafb900789aa9c9f3fb0192a9ea1ae6e5ffb0d231%0A*+Document+last+modified%3A+2021-05-31T00%3A59%3A40.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22ImageData%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/ImageData/contributors.txt)

Change your languageSelect your preferred language English (US)Français日本語한국어Русский中文 (简体)

Change language

#### Related Topics

1.  **[Canvas API](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API)**
2.  **[`ImageData`](https://developer.mozilla.org/en-US/docs/Web/API/ImageData)**
3.  Constructor
    1.  [`ImageData()`](https://developer.mozilla.org/en-US/docs/Web/API/ImageData/ImageData)
4.  Properties
    1.  [`data`](https://developer.mozilla.org/en-US/docs/Web/API/ImageData/data)
    2.  [`height`](https://developer.mozilla.org/en-US/docs/Web/API/ImageData/height)
    3.  [`width`](https://developer.mozilla.org/en-US/docs/Web/API/ImageData/width)
5.  Related pages for Canvas API
    1.  [`Canvas`](https://developer.mozilla.org/en-US/docs/Web/API/Canvas)
    2.  [`CanvasGradient`](https://developer.mozilla.org/en-US/docs/Web/API/CanvasGradient)
    3.  [`CanvasImageSource`](https://developer.mozilla.org/en-US/docs/Web/API/CanvasImageSource)
    4.  [`CanvasPattern`](https://developer.mozilla.org/en-US/docs/Web/API/CanvasPattern)
    5.  [`CanvasRenderingContext2D`](https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D)
    6.  [`HTMLCanvasElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement)
    7.  [`ImageBitmap`](https://developer.mozilla.org/en-US/docs/Web/API/ImageBitmap)
    8.  [`ImageBitmapFactories`](https://developer.mozilla.org/en-US/docs/Web/API/ImageBitmapFactories)
    9.  [`ImageBitmapRenderingContext`](https://developer.mozilla.org/en-US/docs/Web/API/ImageBitmapRenderingContext)
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
