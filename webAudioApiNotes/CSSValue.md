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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSValue" class="breadcrumb-current-page"><span data-property="name">CSSValue</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Properties](#properties)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

CSSValue
========

#### Deprecated

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `CSSValue` interface represents the current computed value of a CSS property.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

[`CSSValue.cssText`](https://developer.mozilla.org/en-US/docs/Web/API/CSSValue/cssText)  
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) representing the current value.

[`CSSValue.cssValueType`](https://developer.mozilla.org/en-US/docs/Web/API/CSSValue/cssValueType)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
An `unsigned short` representing a code defining the type of the value. Possible values are:

<table><tbody><tr class="odd"><td>Constant</td><td>Description</td></tr><tr class="even"><td><code>CSS_CUSTOM</code></td><td>The value is a custom value.</td></tr><tr class="odd"><td><code>CSS_INHERIT</code></td><td>The value is inherited and the <code>cssText</code> contains <code>"inherit"</code>.</td></tr><tr class="even"><td><code>CSS_PRIMITIVE_VALUE</code></td><td>The value is a primitive value and an instance of the <a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSPrimitiveValue"><code>CSSPrimitiveValue</code></a> interface can be obtained by using binding-specific casting methods on this instance of the <code>CSSValue</code> interface.</td></tr><tr class="odd"><td><code>CSS_VALUE_LIST</code></td><td>The value is a <code>CSSValue</code> list and an instance of the <a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSValueList"><code>CSSValueList</code></a> interface can be obtained by using binding-specific casting methods on this instance of the <code>CSSValue</code> interface.</td></tr></tbody></table>

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Style/css.html#CSS-CSSValue" class="external">Document Object Model (DOM) Level 2 Style Specification<br />
<span class="small">The definition of 'CSSValue' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [`CSSPrimitiveValue`](https://developer.mozilla.org/en-US/docs/Web/API/CSSPrimitiveValue)
-   [`CSSValueList`](https://developer.mozilla.org/en-US/docs/Web/API/CSSValueList)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/cssvalue/index.html "Folder: en-us/web/api/cssvalue (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FCSSValue%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fcssvalue%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FCSSValue%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fcssvalue%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fe085698aeab231f6d0c1d3bb7ea6288237946703%0A*+Document+last+modified%3A+2021-05-29T04%3A16%3A39.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22CSSValue%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 29, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/CSSValue/contributors.txt)

Change your languageSelect your preferred language English (US)Français日本語Русский中文 (简体)

Change language

#### Related Topics

1.  **[CSS Object Model](https://developer.mozilla.org/en-US/docs/Web/API/CSS_Object_Model)**
2.  **[`CSSValue`](https://developer.mozilla.org/en-US/docs/Web/API/CSSValue)**
3.  Properties
    1.  [`cssText`](https://developer.mozilla.org/en-US/docs/Web/API/CSSValue/cssText)
    2.  [`cssValueType`](https://developer.mozilla.org/en-US/docs/Web/API/CSSValue/cssValueType)
4.  Related pages for CSSOM
    1.  [`AnimationEvent`](https://developer.mozilla.org/en-US/docs/Web/API/AnimationEvent)
    2.  [`CSS`](https://developer.mozilla.org/en-US/docs/Web/API/CSS)
    3.  [`CSSConditionRule`](https://developer.mozilla.org/en-US/docs/Web/API/CSSConditionRule)
    4.  [`CSSGroupingRule`](https://developer.mozilla.org/en-US/docs/Web/API/CSSGroupingRule)
    5.  [`CSSKeyframeRule`](https://developer.mozilla.org/en-US/docs/Web/API/CSSKeyframeRule)
    6.  [`CSSKeyframesRule`](https://developer.mozilla.org/en-US/docs/Web/API/CSSKeyframesRule)
    7.  [`CSSMediaRule`](https://developer.mozilla.org/en-US/docs/Web/API/CSSMediaRule)
    8.  [`CSSNamespaceRule`](https://developer.mozilla.org/en-US/docs/Web/API/CSSNamespaceRule)
    9.  [`CSSPageRule`](https://developer.mozilla.org/en-US/docs/Web/API/CSSPageRule)
    10. [`CSSRule`](https://developer.mozilla.org/en-US/docs/Web/API/CSSRule)
    11. [`CSSRuleList`](https://developer.mozilla.org/en-US/docs/Web/API/CSSRuleList)
    12. [`CSSStyleDeclaration`](https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleDeclaration)
    13. [`CSSStyleRule`](https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleRule)
    14. [`CSSStyleSheet`](https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleSheet)
    15. [`CSSSupportsRule`](https://developer.mozilla.org/en-US/docs/Web/API/CSSSupportsRule)
    16. [`CaretPosition`](https://developer.mozilla.org/en-US/docs/Web/API/CaretPosition)
    17. [`LinkStyle`](https://developer.mozilla.org/en-US/docs/Web/API/LinkStyle)
    18. [`MediaQueryList`](https://developer.mozilla.org/en-US/docs/Web/API/MediaQueryList)
    19. [`MediaQueryListListener`](https://developer.mozilla.org/en-US/docs/Web/API/MediaQueryListListener)
    20. [`Screen`](https://developer.mozilla.org/en-US/docs/Web/API/Screen)
    21. [`StyleSheet`](https://developer.mozilla.org/en-US/docs/Web/API/StyleSheet)
    22. [`StyleSheetList`](https://developer.mozilla.org/en-US/docs/Web/API/StyleSheetList)
    23. [`TransitionEvent`](https://developer.mozilla.org/en-US/docs/Web/API/TransitionEvent)

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
