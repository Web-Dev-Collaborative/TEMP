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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMPointReadOnly" class="breadcrumb-current-page"><span data-property="name">DOMPointReadOnly</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Constructor](#constructor)
-   [Properties](#properties)
-   [Static methods](#static_methods)
-   [Methods](#methods)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

DOMPointReadOnly
================

<span class="seoSummary">The **`DOMPointReadOnly`** interface specifies the coordinate and perspective fields used by [`DOMPoint`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPoint) to define a 2D or 3D point in a coordinate system.</span>

**Note:** This feature is available in [Web Workers](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API)

There are two ways to create a new `DOMPointReadOnly` instance. First, you can use its constructor, passing in the values of the parameters for each dimension and, optionally, the perspective:

    /* 2D */
    const point = new DOMPointReadOnly(50, 50);

    /* 3D */
    const point = new DOMPointReadOnly(50, 50, 25);

    /* 3D with perspective */
    const point = new DOMPointReadOnly(100, 100, 100, 1.0);

The other option is to use the static [`DOMPointReadOnly.fromPoint()`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPointReadOnly/fromPoint) method:

    const point = DOMPointReadOnly.fromPoint({x: 100, y: 100, z: 50; w: 1.0});

[Constructor](#constructor "Permalink to Constructor")
------------------------------------------------------

[`DOMPointReadOnly()`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPointReadOnly/DOMPointReadOnly "DOMPointReadOnly()")  
Creates a new `DOMPointReadOnly` object given the values of its coordinates and perspective. To create a point using a`DOMPointInit` object, you can instead use [`DOMPointReadOnly.fromPoint()`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPointReadOnly/fromPoint).

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

[`DOMPointReadOnly.x`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPointReadOnly/x) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
The point's horizontal coordinate, `x`.

[`DOMPointReadOnly.y`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPointReadOnly/y) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
The point's vertical coordinate, `y`.

[`DOMPointReadOnly.z`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPointReadOnly/z) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
The point's depth coordinate, `z`.

[`DOMPointReadOnly.w`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPointReadOnly/w) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
The point's perspective value, `w`.

[Static methods](#static_methods "Permalink to Static methods")
---------------------------------------------------------------

[`DOMPointReadOnly.fromPoint()`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPointReadOnly/fromPoint)  
A static method that creates a new `DOMPointReadOnly` object given the coordinates provided in the specified [`DOMPointInit`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPointInit) object.

[Methods](#methods "Permalink to Methods")
------------------------------------------

<span class="page-not-created">`matrixTransform()`</span>  
Applies a matrix transform specified as a <span class="page-not-created">`DOMMatrixInit`</span> object to the `DOMPointReadOnly` object.

[`toJSON()`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPointReadOnly/toJSON "toJSON()")  
Returns a JSON representation of the `DOMPointReadOnly` object.

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/geometry/#DOMPoint" class="external">Geometry Interfaces Module Level 1<br />
<span class="small">The definition of 'DOMPoint' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Latest spec version is an ED.</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [`DOMPoint`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPoint)
-   [`DOMRect`](https://developer.mozilla.org/en-US/docs/Web/API/DOMRect)
-   [`DOMMatrix`](https://developer.mozilla.org/en-US/docs/Web/API/DOMMatrix)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/dompointreadonly/index.html "Folder: en-us/web/api/dompointreadonly (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FDOMPointReadOnly%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fdompointreadonly%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FDOMPointReadOnly%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fdompointreadonly%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Ffffe339bce9adcb9ced09d1d5eff291c105ce6ad%0A*+Document+last+modified%3A+2021-05-29T05%3A32%3A06.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22DOMPointReadOnly%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 29, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/DOMPointReadOnly/contributors.txt)

Change your languageSelect your preferred language English (US)Français

Change language

#### Related Topics

1.  **[`DOMPointReadOnly`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPointReadOnly)**
2.  Constructor
    1.  [`DOMPointReadOnly()`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPointReadOnly/DOMPointReadOnly)
3.  Properties
    1.  [`w`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPointReadOnly/w)
    2.  [`x`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPointReadOnly/x)
    3.  [`y`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPointReadOnly/y)
    4.  [`z`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPointReadOnly/z)
4.  Methods
    1.  [`fromPoint()`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPointReadOnly/fromPoint)
    2.  [`toJSON()`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPointReadOnly/toJSON)
5.  Related pages for Geometry Interfaces
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
