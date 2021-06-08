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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSPrimitiveValue" class="breadcrumb-current-page"><span data-property="name">CSSPrimitiveValue</span></a>

Table of contents
-----------------

Table of contents

-   [Properties](#properties)
-   [Methods](#methods)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

CSSPrimitiveValue
=================

#### Deprecated

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `CSSPrimitiveValue` interface derives from the [`CSSValue`](https://developer.mozilla.org/en-US/docs/Web/API/CSSValue) interface and represents the current computed value of a CSS property.

This interface represents a single CSS value. It may be used to determine the value of a specific style property currently set in a block or to set a specific style property explicitly within the block. An instance of this interface might be obtained from the [`getPropertyCSSValue()`](https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleDeclaration/getPropertyCSSValue "getPropertyCSSValue()") method of the [`CSSStyleDeclaration`](https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleDeclaration) interface. A `CSSPrimitiveValue` object only occurs in a context of a CSS property.

Conversions are allowed between absolute values (from millimeters to centimeters, from degrees to radians, and so on) but not between relative values. (For example, a pixel value cannot be converted to a centimeter value.) Percentage values can't be converted since they are relative to the parent value (or another property value). There is one exception for color percentage values: since a color percentage value is relative to the range 0-255, a color percentage value can be converted to a number (see also the <span class="page-not-created">`RGBColor`</span> interface).

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

*Inherits properties from its parent, `CSSValue`*.

[`CSSPrimitiveValue.primitiveType`](https://developer.mozilla.org/en-US/docs/Web/API/CSSPrimitiveValue/primitiveType) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
An `unsigned short` representing the type of the value. Possible values are:

<table><tbody><tr class="odd"><td>Constant</td><td>Description</td></tr><tr class="even"><td><code>CSS_ATTR</code></td><td>The value is an <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/attr()"><code>attr()</code></a> function. The value can be obtained by using the <code>getStringValue()</code> method.</td></tr><tr class="odd"><td><code>CSS_CM</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/length"><code>&lt;length&gt;</code></a> in centimeters. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="even"><td><code>CSS_COUNTER</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Lists_and_Counters/Using_CSS_counters">counter or counters</a> function. The value can be obtained by using the <code>getCounterValue()</code> method.</td></tr><tr class="odd"><td><code>CSS_DEG</code></td><td>The value is an <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/angle"><code>&lt;angle&gt;</code></a> in degrees. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="even"><td><code>CSS_DIMENSION</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/number"><code>&lt;number&gt;</code></a> with an unknown dimension. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="odd"><td><code>CSS_EMS</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/length"><code>&lt;length&gt;</code></a> in em units. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="even"><td><code>CSS_EXS</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/length"><code>&lt;length&gt;</code></a> in ex units. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="odd"><td><code>CSS_GRAD</code></td><td>The value is an <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/angle"><code>&lt;angle&gt;</code></a> in grads. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="even"><td><code>CSS_HZ</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/frequency"><code>&lt;frequency&gt;</code></a> in Hertz. The value can be obtained by using the getFloatValue method.</td></tr><tr class="odd"><td><code>CSS_IDENT</code></td><td>The value is an identifier. The value can be obtained by using the <code>getStringValue()</code> method.</td></tr><tr class="even"><td><code>CSS_IN</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/length"><code>&lt;length&gt;</code></a> in inches. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="odd"><td><code>CSS_KHZ</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/frequency"><code>&lt;frequency&gt;</code></a> in Kilohertz. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="even"><td><code>CSS_MM</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/length"><code>&lt;length&gt;</code></a> in millimeters. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="odd"><td><code>CSS_MS</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/time"><code>&lt;time&gt;</code></a> in milliseconds. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="even"><td><code>CSS_NUMBER</code></td><td>The value is a simple <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/number"><code>&lt;number&gt;</code></a>. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="odd"><td><code>CSS_PC</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/length"><code>&lt;length&gt;</code></a> in picas. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="even"><td><code>CSS_PERCENTAGE</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/percentage"><code>&lt;percentage&gt;</code></a>. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="odd"><td><code>CSS_PT</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/length"><code>&lt;length&gt;</code></a> in points. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="even"><td><code>CSS_PX</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/length"><code>&lt;length&gt;</code></a> in pixels. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="odd"><td><code>CSS_RAD</code></td><td>The value is an <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/angle"><code>&lt;angle&gt;</code></a> in radians. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="even"><td><code>CSS_RECT</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/shape#syntax"><code>rect()</code></a> function. The value can be obtained by using the <code>getRectValue()</code> method.</td></tr><tr class="odd"><td><code>CSS_RGBCOLOR</code></td><td>The value is an <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/color_value"><code>&lt;color&gt;</code></a>. The value can be obtained by using the <code>getRGBColorValue()</code> method.</td></tr><tr class="even"><td><code>CSS_S</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/time"><code>&lt;time&gt;</code></a> in seconds. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="odd"><td><code>CSS_STRING</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/string"><code>&lt;string&gt;</code></a>. The value can be obtained by using the <code>getStringValue()</code> method.</td></tr><tr class="even"><td><code>CSS_UNKNOWN</code></td><td>The value is not a recognized CSS2 value. The value can only be obtained by using the <a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSValue/cssText" title="cssText"><code>cssText</code></a> attribute.</td></tr><tr class="odd"><td><code>CSS_URI</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/url()"><code>url()</code></a>. The value can be obtained by using the <code>getStringValue()</code> method.</td></tr></tbody></table>

[Methods](#methods "Permalink to Methods")
------------------------------------------

[`CSSPrimitiveValue.getCounterValue()`](https://developer.mozilla.org/en-US/docs/Web/API/CSSPrimitiveValue/getCounterValue)  
This method is used to get the [counter](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Lists_and_Counters/Using_CSS_counters) value. If this CSS value doesn't contain a counter value, a [`DOMException`](https://developer.mozilla.org/en-US/docs/Web/API/DOMException) is raised. Modification to the corresponding style property can be achieved using the <span class="page-not-created">`Counter`</span> interface.

[`CSSPrimitiveValue.getFloatValue()`](https://developer.mozilla.org/en-US/docs/Web/API/CSSPrimitiveValue/getFloatValue)  
This method is used to get a float value in a specified unit. If this CSS value doesn't contain a float value or can't be converted into the specified unit, a [`DOMException`](https://developer.mozilla.org/en-US/docs/Web/API/DOMException) is raised.

[`CSSPrimitiveValue.getRGBColorValue()`](https://developer.mozilla.org/en-US/docs/Web/API/CSSPrimitiveValue/getRGBColorValue)  
This method is used to get the RGB color. If this CSS value doesn't contain a RGB color value, a [`DOMException`](https://developer.mozilla.org/en-US/docs/Web/API/DOMException) is raised. Modification to the corresponding style property can be achieved using the <span class="page-not-created">`RGBColor`</span> interface.

[`CSSPrimitiveValue.getRectValue()`](https://developer.mozilla.org/en-US/docs/Web/API/CSSPrimitiveValue/getRectValue)  
This method is used to get the Rect value. If this CSS value doesn't contain a rect value, a [`DOMException`](https://developer.mozilla.org/en-US/docs/Web/API/DOMException) is raised. Modification to the corresponding style property can be achieved using the <span class="page-not-created">`Rect`</span> interface.

[`CSSPrimitiveValue.getStringValue()`](https://developer.mozilla.org/en-US/docs/Web/API/CSSPrimitiveValue/getStringValue)  
This method is used to get the string value. If the CSS value doesn't contain a string value, a [`DOMException`](https://developer.mozilla.org/en-US/docs/Web/API/DOMException) is raised.

[`CSSPrimitiveValue.setFloatValue()`](https://developer.mozilla.org/en-US/docs/Web/API/CSSPrimitiveValue/setFloatValue)  
A method to set the float value with a specified unit. If the property attached with this value can not accept the specified unit or the float value, the value will be unchanged and a [`DOMException`](https://developer.mozilla.org/en-US/docs/Web/API/DOMException) will be raised.

[`CSSPrimitiveValue.setStringValue()`](https://developer.mozilla.org/en-US/docs/Web/API/CSSPrimitiveValue/setStringValue)  
A method to set the string value with the specified unit. If the property attached to this value can't accept the specified unit or the string value, the value will be unchanged and a [`DOMException`](https://developer.mozilla.org/en-US/docs/Web/API/DOMException) will be raised.

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Style/css.html#CSS-CSSPrimitiveValue" class="external">Document Object Model (DOM) Level 2 Style Specification<br />
<span class="small">The definition of 'CSSPrimitiveValue' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [`CSSValue`](https://developer.mozilla.org/en-US/docs/Web/API/CSSValue)
-   [`CSSValueList`](https://developer.mozilla.org/en-US/docs/Web/API/CSSValueList)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/cssprimitivevalue/index.html "Folder: en-us/web/api/cssprimitivevalue (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FCSSPrimitiveValue%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fcssprimitivevalue%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FCSSPrimitiveValue%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fcssprimitivevalue%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fe085698aeab231f6d0c1d3bb7ea6288237946703%0A*+Document+last+modified%3A+2021-05-29T04%3A16%3A39.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22CSSPrimitiveValue%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 29, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/CSSPrimitiveValue/contributors.txt)

#### Related Topics

1.  **[CSS Object Model](https://developer.mozilla.org/en-US/docs/Web/API/CSS_Object_Model)**
2.  **[`CSSPrimitiveValue`](https://developer.mozilla.org/en-US/docs/Web/API/CSSPrimitiveValue)**
3.  Properties
    1.  [`primitiveType`](https://developer.mozilla.org/en-US/docs/Web/API/CSSPrimitiveValue/primitiveType)
4.  Methods
    1.  [`getCounterValue()`](https://developer.mozilla.org/en-US/docs/Web/API/CSSPrimitiveValue/getCounterValue)
    2.  [`getFloatValue()`](https://developer.mozilla.org/en-US/docs/Web/API/CSSPrimitiveValue/getFloatValue)
    3.  [`getRectValue()`](https://developer.mozilla.org/en-US/docs/Web/API/CSSPrimitiveValue/getRectValue)
    4.  [`getRGBColorValue()`](https://developer.mozilla.org/en-US/docs/Web/API/CSSPrimitiveValue/getRGBColorValue)
    5.  [`getStringValue()`](https://developer.mozilla.org/en-US/docs/Web/API/CSSPrimitiveValue/getStringValue)
    6.  [`setFloatValue()`](https://developer.mozilla.org/en-US/docs/Web/API/CSSPrimitiveValue/setFloatValue)
    7.  [`setStringValue()`](https://developer.mozilla.org/en-US/docs/Web/API/CSSPrimitiveValue/setStringValue)
5.  Inheritance:
    1.  [`CSSValue`](https://developer.mozilla.org/en-US/docs/Web/API/CSSValue)
6.  Related pages for CSSOM
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
