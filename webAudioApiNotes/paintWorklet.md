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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/CSS" class="breadcrumb-penultimate"><span data-property="name">CSS</span></a>
4.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/CSS/paintWorklet" class="breadcrumb-current-page"><span data-property="name">CSS.paintWorklet (Static property)</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Syntax](#syntax)
-   [Examples](#examples)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

CSS.paintWorklet (Static property)
==================================

#### Draft

This page is not complete.

#### Experimental

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

#### Secure context

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

<span class="seoSummary">**`paintWorklet`** is a static, read-only property of the [`CSS`](https://developer.mozilla.org/en-US/docs/Web/API/CSS) interface that provides access to the [`PaintWorklet`](https://developer.mozilla.org/en-US/docs/Web/API/PaintWorklet), which programmatically generates an image where a CSS property expects a file.</span>

[Syntax](#syntax "Permalink to Syntax")
---------------------------------------

    var worklet = CSS.paintWorklet;

### [Value](#value "Permalink to Value")

The [`PaintWorklet`](https://developer.mozilla.org/en-US/docs/Web/API/PaintWorklet) object.

[Examples](#examples "Permalink to Examples")
---------------------------------------------

The following example demonstrates loading a [`PaintWorklet`](https://developer.mozilla.org/en-US/docs/Web/API/PaintWorklet) from its js file and does so by feature detection. 

    <script>
      if ('paintWorklet' in CSS) {
        CSS.paintWorklet.addModule('checkerboard.js');
      }
    </script>

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-paint-api-1/#dom-css-paintworklet" class="external">CSS Painting API Level 1<br />
<span class="small">The definition of 'paintWorklet' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [CSS Painting API](https://developer.mozilla.org/en-US/docs/Web/API/CSS_Painting_API)
-   [Houdini APIs](https://developer.mozilla.org/en-US/docs/Web/Houdini)
-   <a href="https://developer.mozilla.org/en-US/docs/Web/Houdini/learn" class="page-not-created" title="This is a link to an unwritten page">Houdini overview</a>

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/css/paintworklet/index.html "Folder: en-us/web/api/css/paintworklet (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FCSS%2FpaintWorklet%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fcss%2Fpaintworklet%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FCSS%2FpaintWorklet%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fcss%2Fpaintworklet%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fe085698aeab231f6d0c1d3bb7ea6288237946703%0A*+Document+last+modified%3A+2021-05-29T04%3A16%3A39.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22CSS.paintWorklet+%28Static+property%29%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 29, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/CSS/paintWorklet/contributors.txt)

Change your languageSelect your preferred language English (US)日本語

Change language

#### Related Topics

1.  **[CSS Object Model](https://developer.mozilla.org/en-US/docs/Web/API/CSS_Object_Model)**
2.  **[`CSS`](https://developer.mozilla.org/en-US/docs/Web/API/CSS)**
3.  Properties
    1.  *`paintWorklet (Static property)`*
4.  Methods
    1.  [`escape()`](https://developer.mozilla.org/en-US/docs/Web/API/CSS/escape)
    2.  [`supports()`](https://developer.mozilla.org/en-US/docs/Web/API/CSS/supports)
5.  Related pages for CSSOM
    1.  [`AnimationEvent`](https://developer.mozilla.org/en-US/docs/Web/API/AnimationEvent)
    2.  [`CSSConditionRule`](https://developer.mozilla.org/en-US/docs/Web/API/CSSConditionRule)
    3.  [`CSSGroupingRule`](https://developer.mozilla.org/en-US/docs/Web/API/CSSGroupingRule)
    4.  [`CSSKeyframeRule`](https://developer.mozilla.org/en-US/docs/Web/API/CSSKeyframeRule)
    5.  [`CSSKeyframesRule`](https://developer.mozilla.org/en-US/docs/Web/API/CSSKeyframesRule)
    6.  [`CSSMediaRule`](https://developer.mozilla.org/en-US/docs/Web/API/CSSMediaRule)
    7.  [`CSSNamespaceRule`](https://developer.mozilla.org/en-US/docs/Web/API/CSSNamespaceRule)
    8.  [`CSSPageRule`](https://developer.mozilla.org/en-US/docs/Web/API/CSSPageRule)
    9.  [`CSSRule`](https://developer.mozilla.org/en-US/docs/Web/API/CSSRule)
    10. [`CSSRuleList`](https://developer.mozilla.org/en-US/docs/Web/API/CSSRuleList)
    11. [`CSSStyleDeclaration`](https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleDeclaration)
    12. [`CSSStyleRule`](https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleRule)
    13. [`CSSStyleSheet`](https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleSheet)
    14. [`CSSSupportsRule`](https://developer.mozilla.org/en-US/docs/Web/API/CSSSupportsRule)
    15. [`CaretPosition`](https://developer.mozilla.org/en-US/docs/Web/API/CaretPosition)
    16. [`LinkStyle`](https://developer.mozilla.org/en-US/docs/Web/API/LinkStyle)
    17. [`MediaQueryList`](https://developer.mozilla.org/en-US/docs/Web/API/MediaQueryList)
    18. [`MediaQueryListListener`](https://developer.mozilla.org/en-US/docs/Web/API/MediaQueryListListener)
    19. [`Screen`](https://developer.mozilla.org/en-US/docs/Web/API/Screen)
    20. [`StyleSheet`](https://developer.mozilla.org/en-US/docs/Web/API/StyleSheet)
    21. [`StyleSheetList`](https://developer.mozilla.org/en-US/docs/Web/API/StyleSheetList)
    22. [`TransitionEvent`](https://developer.mozilla.org/en-US/docs/Web/API/TransitionEvent)

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
