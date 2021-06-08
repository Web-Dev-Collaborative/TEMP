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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMRect" class="breadcrumb-current-page"><span data-property="name">DOMRect</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Constructor](#constructor)
-   [Properties](#properties)
-   [Methods](#methods)
-   [Static methods](#static_methods)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

DOMRect
=======

#### Draft

This page is not complete.

A **`DOMRect`** describes the size and position of a rectangle.

The type of box represented by the `DOMRect` is specified by the method or property that returned it. For example, [`VREyeParameters.renderRect`](https://developer.mozilla.org/en-US/docs/Web/API/VREyeParameters/renderRect) from the WebVR API specifies the viewport of a [canvas](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement) into which visuals for one eye of a head mounted display should be rendered.

It inherits from its parent, [`DOMRectReadOnly`](https://developer.mozilla.org/en-US/docs/Web/API/DOMRectReadOnly).

[Constructor](#constructor "Permalink to Constructor")
------------------------------------------------------

[`DOMRect()`](https://developer.mozilla.org/en-US/docs/Web/API/DOMRect/DOMRect "DOMRect()")  
Creates a new `DOMRect` object.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

*`DOMRect` inherits properties from its parent, [`DOMRectReadOnly`](https://developer.mozilla.org/en-US/docs/Web/API/DOMRectReadOnly). The difference is that they are not read-only anymore.*

[`DOMRectReadOnly.x`](https://developer.mozilla.org/en-US/docs/Web/API/DOMRectReadOnly/x)  
The x coordinate of the `DOMRect`'s origin (typically the top-left corner of the rectangle).

[`DOMRectReadOnly.y`](https://developer.mozilla.org/en-US/docs/Web/API/DOMRectReadOnly/y)  
The y coordinate of the `DOMRect`'s origin (typically the top-left corner of the rectangle).

[`DOMRectReadOnly.width`](https://developer.mozilla.org/en-US/docs/Web/API/DOMRectReadOnly/width)  
The width of the `DOMRect`.

[`DOMRectReadOnly.height`](https://developer.mozilla.org/en-US/docs/Web/API/DOMRectReadOnly/height)  
The height of the `DOMRect`.

[`DOMRectReadOnly.top`](https://developer.mozilla.org/en-US/docs/Web/API/DOMRectReadOnly/top)  
Returns the top coordinate value of the `DOMRect` (has the same value as `y`, or `y + height` if `height` is negative.)

[`DOMRectReadOnly.right`](https://developer.mozilla.org/en-US/docs/Web/API/DOMRectReadOnly/right)  
Returns the right coordinate value of the `DOMRect` (has the same value as `x + width`, or `x` if `width` is negative.)

[`DOMRectReadOnly.bottom`](https://developer.mozilla.org/en-US/docs/Web/API/DOMRectReadOnly/bottom)  
Returns the bottom coordinate value of the `DOMRect` (has the same value as `y + height`, or `y` if `height` is negative.)

[`DOMRectReadOnly.left`](https://developer.mozilla.org/en-US/docs/Web/API/DOMRectReadOnly/left)  
Returns the left coordinate value of the `DOMRect` (has the same value as `x`, or `x + width` if `width` is negative.)

[Methods](#methods "Permalink to Methods")
------------------------------------------

*`DOMRect` inherits methods from its parent, [`DOMRectReadOnly`](https://developer.mozilla.org/en-US/docs/Web/API/DOMRectReadOnly).*

[Static methods](#static_methods "Permalink to Static methods")
---------------------------------------------------------------

[`DOMRectReadOnly.fromRect()`](https://developer.mozilla.org/en-US/docs/Web/API/DOMRectReadOnly/fromRect)  
Creates a new `DOMRect` object with a given location and dimensions.

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/geometry/#DOMRect" class="external">Geometry Interfaces Module Level 1<br />
<span class="small">The definition of 'DOMRect' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [`DOMPoint`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPoint)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/domrect/index.html "Folder: en-us/web/api/domrect (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FDOMRect%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fdomrect%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FDOMRect%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fdomrect%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Ffffe339bce9adcb9ced09d1d5eff291c105ce6ad%0A*+Document+last+modified%3A+2021-05-29T05%3A32%3A06.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22DOMRect%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 29, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/DOMRect/contributors.txt)

Change your languageSelect your preferred language English (US)Français中文 (简体)

Change language

#### Related Topics

1.  **[`DOMRect`](https://developer.mozilla.org/en-US/docs/Web/API/DOMRect)**
2.  Constructor
    1.  [`DOMRect()`](https://developer.mozilla.org/en-US/docs/Web/API/DOMRect/DOMRect)
3.  Inheritance:
    1.  [`DOMRectReadOnly`](https://developer.mozilla.org/en-US/docs/Web/API/DOMRectReadOnly)
4.  Related pages for Geometry Interfaces
    1.  [`CSSMatrix`](https://developer.mozilla.org/en-US/docs/Web/API/CSSMatrix)
    2.  [`DOMMatrix`](https://developer.mozilla.org/en-US/docs/Web/API/DOMMatrix)
    3.  [`DOMMatrixReadOnly`](https://developer.mozilla.org/en-US/docs/Web/API/DOMMatrixReadOnly)
    4.  [`Point`](https://developer.mozilla.org/en-US/docs/Web/API/Point)

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
