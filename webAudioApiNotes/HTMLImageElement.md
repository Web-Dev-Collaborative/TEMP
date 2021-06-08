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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement" class="breadcrumb-current-page"><span data-property="name">HTMLImageElement</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Constructor](#constructor)
-   [Properties](#properties)
-   [Obsolete properties](#obsolete_properties)
-   [Methods](#methods)
-   [Errors](#errors)
-   [Example](#example)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

HTMLImageElement
================

<span class="seoSummary">The **`HTMLImageElement`** interface represents an HTML [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) element, providing the properties and methods used to manipulate image elements.</span>

[Constructor](#constructor "Permalink to Constructor")
------------------------------------------------------

[`Image()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/Image "Image()")  
The `Image()` constructor creates and returns a new `HTMLImageElement` object representing an HTML [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) element which is not attached to any DOM tree. It accepts optional width and height parameters. When called without parameters, `new ``Image()` is equivalent to calling [`document.createElement("img")`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createElement "document.createElement(").

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

*Inherits properties from its parent, [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement).*

[`HTMLImageElement.alt`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/alt)  
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) that reflects the [`alt`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#attr-alt) HTML attribute, thus indicating the alternate fallback content to be displayed if the image has not been loaded.

[`HTMLImageElement.complete`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/complete) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that is `true` if the browser has finished fetching the image, whether successful or not. That means this value is also `true` if the image has no [`src`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/src "src") value indicating an image to load.

[`HTMLImageElement.crossOrigin`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/crossOrigin)  
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) specifying the CORS setting for this image element. See [CORS settings attributes](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/crossorigin) for further details. This may be `null` if CORS is not used.

[`HTMLImageElement.currentSrc`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/currentSrc) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString) representing the URL from which the currently displayed image was loaded. This may change as the image is adjusted due to changing conditions, as directed by any [media queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries) which are in place.

[`HTMLImageElement.decoding`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/decoding)  
An optional [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) representing a hint given to the browser on how it should decode the image. If this value is provided, it must be one of the possible permitted values: `sync` to decode the image synchronously, `async` to decode it asynchronously, or `auto` to indicate no preference (which is the default). Read the [`decoding`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/decoding "decoding") page for details on the implications of this property's values.

[`HTMLImageElement.height`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/height)  
An integer value that reflects the [`height`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#attr-height) HTML attribute, indicating the rendered height of the image in CSS pixels.

[`HTMLImageElement.isMap`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/isMap)  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that reflects the [`ismap`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#attr-ismap) HTML attribute, indicating that the image is part of a server-side image map. This is different from a client-side image map, specified using an `<img>` element and a corresponding [`<map>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/map) which contains [`<area>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/area) elements indicating the clickable areas in the image. The image *must* be contained within an [`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a) element; see the `ismap` page for details.

[`HTMLImageElement.loading`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/loading)  
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) providing a hint to the browser used to optimize loading the document by determining whether to load the image immediately (`eager`) or on an as-needed basis (`lazy`).

[`HTMLImageElement.naturalHeight`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/naturalHeight) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns an integer value representing the intrinsic height of the image in CSS pixels, if it is available; else, it shows `0`. This is the height the image would be if it were rendered at its natural full size.

[`HTMLImageElement.naturalWidth`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/naturalWidth) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
An integer value representing the intrinsic width of the image in CSS pixels, if it is available; otherwise, it will show `0`. This is the width the image would be if it were rendered at its natural full size.

[`HTMLImageElement.referrerPolicy`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/referrerPolicy)  
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) that reflects the [`referrerpolicy`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#attr-referrerpolicy) HTML attribute, which tells the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) how to decide which referrer to use in order to fetch the image. Read this article for details on the possible values of this string.

[`HTMLImageElement.sizes`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/sizes)  
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the [`sizes`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#attr-sizes) HTML attribute. This string specifies a list of comma-separated conditional sizes for the image; that is, for a given viewport size, a particular image size is to be used. Read the documentation on the [`sizes`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/sizes "sizes") page for details on the format of this string.

[`HTMLImageElement.src`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/src)  
A [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString) that reflects the [`src`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#attr-src) HTML attribute, which contains the full URL of the image including base URI. You can load a different image into the element by changing the URL in the `src` attribute.

[`HTMLImageElement.srcset`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/srcset)  
A [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString) reflecting the [`srcset`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#attr-srcset) HTML attribute. This specifies a list of candidate images, separated by commas (`',', U+002C COMMA`). Each candidate image is a URL followed by a space, followed by a specially-formatted string indicating the size of the image. The size may be specified either the width or a size multiple. Read the [`srcset`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/srcset "srcset") page for specifics on the format of the size substring.

[`HTMLImageElement.useMap`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/useMap)  
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the [`usemap`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#attr-usemap) HTML attribute, containing the page-local URL of the [`<map>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/map) element describing the image map to use. The page-local URL is a pound (hash) symbol (`#`) followed by the ID of the `<map>` element, such as `#my-map-element`. The `<map>` in turn contains [`<area>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/area) elements indicating the clickable areas in the image.

[`HTMLImageElement.width`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/width)  
An integer value that reflects the [`width`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#attr-width) HTML attribute, indicating the rendered width of the image in CSS pixels.

[`HTMLImageElement.x`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/x) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
An integer indicating the horizontal offset of the left border edge of the image's CSS layout box relative to the origin of the [`<html>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/html) element's containing block.

[`HTMLImageElement.y`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/y) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
The integer vertical offset of the top border edge of the image's CSS layout box relative to the origin of the [`<html>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/html) element's containing block.

[Obsolete properties](#obsolete_properties "Permalink to Obsolete properties")
------------------------------------------------------------------------------

[`HTMLImageElement.align`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/align)   
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) indicating the alignment of the image with respect to the surrounding context. The possible values are `"left"`, `"right"`, `"justify"`, and `"center"`. This is obsolete; you should instead use CSS (such as [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align), which works with images despite its name) to specify the alignment.

[`HTMLImageElement.border`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/border)   
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) which defines the width of the border surrounding the image. This is deprecated; use the CSS [`border`](https://developer.mozilla.org/en-US/docs/Web/CSS/border) property instead.

[`HTMLImageElement.hspace`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/hspace)   
An integer value which specifies the amount of space (in pixels) to leave empty on the left and right sides of the image.

[`HTMLImageElement.longDesc`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/longDesc)   
A [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString) specifying the URL at which a long description of the image's contents may be found. This is used to turn the image into a hyperlink automatically. Modern HTML should instead place an `<img>` inside an [`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a) element defining the hyperlink.

[`HTMLImageElement.lowsrc`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/lowSrc)   
A [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString) specifying the URL of a low-quality (but faster to load) version of the same image. This was once used by browsers under constrained network conditions or on slow devices.

[`HTMLImageElement.name`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/name)   
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) representing the name of the element.

[`HTMLImageElement.vspace`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/vspace)   
An integer value specifying the amount of empty space, in pixels, to leave above and below the image.

[Methods](#methods "Permalink to Methods")
------------------------------------------

*Inherits properties from its parent, [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement).*

[`HTMLImageElement.decode()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/decode)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves when the image is decoded and it's safe to append the image to the DOM. This prevents rendering of the next frame from having to pause to decode the image, as would happen if an undecoded image were added to the DOM.

[Errors](#errors "Permalink to Errors")
---------------------------------------

If an error occurs while trying to load or render the image, and an [`onerror`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#attr-onerror) event handler has been configured to handle the `error` event, that event handler will get called. This can happen in a number of situations, including:

-   The [`src`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#attr-src) attribute is empty or `null`.
-   The specified `src` URL is the same as the URL of the page the user is currently on.
-   The specified image is corrupted in some way that prevents it from being loaded.
-   The specified image's metadata is corrupted in such a way that it's impossible to retrieve its dimensions, and no dimensions were specified in the `<img>` element's attributes.
-   The specified image is in a format not supported by the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent).

[Example](#example "Permalink to Example")
------------------------------------------

    var img1 = new Image(); // Image constructor
    img1.src = 'image1.png';
    img1.alt = 'alt';
    document.body.appendChild(img1);

    var img2 = document.createElement('img'); // Use DOM HTMLImageElement
    img2.src = 'image2.jpg';
    img2.alt = 'alt text';
    document.body.appendChild(img2);

    // using first image in the document
    alert(document.images[0].src);

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#extensions-to-the-htmlimageelement-interface" class="external">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'Extensions to HTMLImageElement' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Added the <code>x</code> and <code>y</code> properties.</td></tr><tr class="even"><td><a href="https://html.spec.whatwg.org/multipage/#htmlimageelement" class="external">HTML Living Standard<br />
<span class="small">The definition of 'HTMLImageElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>The following properties have been added: <code>srcset</code>, <code>currentSrc</code> and <code>sizes</code>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/embedded-content-0.html#the-img-element" class="external">HTML5<br />
<span class="small">The definition of 'HTMLImageElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>A constructor (with 2 optional parameters) has been added.<br />
The following properties are now obsolete: <code>name</code>, <code>border</code>, <code>align</code>, <code>hspace</code>, <code>vspace</code>, and <code>longdesc</code>.<br />
The following properties are now <code>unsigned long</code>, instead of <code>long</code>: <code>height</code>, and <code>width</code>.<br />
The following properties have been added: <code>crossorigin</code>, <code>naturalWidth</code>, <code>naturalHeight</code>, and <code>complete</code>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-17701901" class="external">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'HTMLImgElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>The <code>lowsrc</code> property has been removed.<br />
The following properties are now <code>long</code>, instead of <code>DOMString</code>: <code>height</code>, <code>width</code>, <code>hspace</code>, and <code>vspace</code>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-html.html#ID-17701901" class="external">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'HTMLImgElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   The HTML element implementing this interface: [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/htmlimageelement/index.html "Folder: en-us/web/api/htmlimageelement (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FHTMLImageElement%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fhtmlimageelement%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FHTMLImageElement%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fhtmlimageelement%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fcb20a8045f6cbdbd224b1068e46c8644470dd8c3%0A*+Document+last+modified%3A+2021-06-01T09%3A10%3A31.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22HTMLImageElement%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Jun 1, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/contributors.txt)

Change your languageSelect your preferred language English (US)EspañolFrançaisРусский中文 (简体)正體中文 (繁體)

Change language

#### Related Topics

1.  **[`HTMLImageElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement)**
2.  Constructor
    1.  [`Image()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/Image)
3.  Properties
    1.  [`align`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/align)
    2.  [`alt`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/alt)
    3.  [`border`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/border)
    4.  [`complete`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/complete)
    5.  [`crossOrigin`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/crossOrigin)
    6.  [`currentSrc`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/currentSrc)
    7.  [`decoding`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/decoding)
    8.  [`height`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/height)
    9.  [`hspace`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/hspace)
    10. [`loading`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/loading)
    11. [`longDesc`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/longDesc)
    12. [`lowsrc`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/lowSrc)
    13. [`name`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/name)
    14. [`naturalWidth`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/naturalWidth)
    15. [`referrerPolicy`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/referrerPolicy)
    16. [`sizes`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/sizes)
    17. [`srcset`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/srcset)
    18. [`useMap`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/useMap)
    19. [`vspace`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/vspace)
    20. [`width`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/width)
4.  Methods
    1.  [`decode()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/decode)
5.  Inheritance:
    1.  [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
    2.  [`Element`](https://developer.mozilla.org/en-US/docs/Web/API/Element)
    3.  [`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node)
    4.  [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)
6.  Related pages for HTML DOM
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
