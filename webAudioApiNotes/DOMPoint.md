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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMPoint" class="breadcrumb-current-page"><span data-property="name">DOMPoint</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Constructor](#constructor)
-   [Methods](#methods)
-   [Static methods](#static_methods)
-   [Properties](#properties)
-   [Examples](#examples)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

DOMPoint
========

<span class="seoSummary">A **`DOMPoint`** object represents a 2D or 3D point in a coordinate system; it includes values for the coordinates in up to three dimensions, as well as an optional perspective value.</span> `DOMPoint` is based on [`DOMPointReadOnly`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPointReadOnly) but allows its properties' values to be changed.

In general, a positive `x` component represents a position to the right of the origin, a positive `y` component is downward from the origin, and a positive `z` component extends outward from the screen (in other words, toward the user).

[Constructor](#constructor "Permalink to Constructor")
------------------------------------------------------

[`DOMPoint()`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPoint/DOMPoint "DOMPoint()")  
Creates and returns a new `DOMPoint` object given the values of zero or more of its coordinate components and optionally the `w` perspective value. You can also use an existing `DOMPoint` or `DOMPointReadOnly` or a [`DOMPointInit`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPointInit) dictionary to create a new point by calling the [`DOMPoint.fromPoint()`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPoint/fromPoint) static method.

[Methods](#methods "Permalink to Methods")
------------------------------------------

*`DOMPoint` inherits methods from its parent, [`DOMPointReadOnly`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPointReadOnly).*

[Static methods](#static_methods "Permalink to Static methods")
---------------------------------------------------------------

[`DOMPoint.fromPoint()`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPoint/fromPoint "DOMPoint.fromPoint()")  
Creates a new mutable `DOMPoint` object given an existing point (or a [`DOMPointInit`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPointInit) dictionary) which provides the values for its properties.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

*`DOMPoint` inherits properties from its parent, [`DOMPointReadOnly`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPointReadOnly).*

[`DOMPoint.x`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPointReadOnly/x "DOMPoint.x")  
The `x` coordinate of the `DOMPoint`.

[`DOMPoint.y`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPointReadOnly/y "DOMPoint.y")  
The `y` coordinate of the `DOMPoint`.

[`DOMPoint.z`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPointReadOnly/z "DOMPoint.z")  
The `z` coordinate of the `DOMPoint`.

[`DOMPoint.w`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPointReadOnly/w "DOMPoint.w")  
The perspective value of the `DOMPoint`.

[Examples](#examples "Permalink to Examples")
---------------------------------------------

In the [WebXR Device API](https://developer.mozilla.org/en-US/docs/Web/API/WebXR_Device_API), `DOMPointReadOnly` values are used to represent positions and orientations. In the following snippet, the pose of the XR device (such as a VR headset or phone with AR capabilities) can be retrieved by calling using [`XRFrame.getViewerPose()`](https://developer.mozilla.org/en-US/docs/Web/API/XRFrame/getViewerPose) during an [`XRSession`](https://developer.mozilla.org/en-US/docs/Web/API/XRSession) animation frame, then accessing the resulting [`XRPose`](https://developer.mozilla.org/en-US/docs/Web/API/XRPose)'s [`transform`](https://developer.mozilla.org/en-US/docs/Web/API/XRPose/transform "transform") property, which contains two `DOMPointReadOnly` attributes: [`position`](https://developer.mozilla.org/en-US/docs/Web/API/XRRigidTransform/position "position") as a vector and <span class="page-not-created">`orientation`</span> as a quaternion.

    function onXRFrame(time, xrFrame) {
      let viewerPose = xrFrame.getViewerPose(xrReferenceSpace);

      if (viewerPose) {
        let position = viewerPose.transform.position;
        let orientation = viewerPose.transform.orientation;

        console.log('XR Viewer Position: {x: ' + roundToTwo(position.x)
                                     + ', y: ' + roundToTwo(position.y)
                                     + ', z: ' + roundToTwo(position.z));

        console.log('XR Viewer Orientation: {x: ' + roundToTwo(orientation.x)
                                        + ', y: ' + roundToTwo(orientation.y)
                                        + ', z: ' + roundToTwo(orientation.z)
                                        + ', w: ' + roundToTwo(orientation.w));
      }
    }

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/geometry/#DOMPoint" class="external">Geometry Interfaces Module Level 1<br />
<span class="small">The definition of 'DOMPoint' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [`DOMRect`](https://developer.mozilla.org/en-US/docs/Web/API/DOMRect)
-   [`DOMMatrix`](https://developer.mozilla.org/en-US/docs/Web/API/DOMMatrix)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/dompoint/index.html "Folder: en-us/web/api/dompoint (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FDOMPoint%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fdompoint%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FDOMPoint%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fdompoint%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Ffffe339bce9adcb9ced09d1d5eff291c105ce6ad%0A*+Document+last+modified%3A+2021-05-29T05%3A32%3A06.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22DOMPoint%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 29, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/DOMPoint/contributors.txt)

Change your languageSelect your preferred language English (US)Français中文 (简体)

Change language

#### Related Topics

1.  **[Document Object Model](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model)**
2.  **[`DOMPoint`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPoint)**
3.  Constructor
    1.  [`DOMPoint()`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPoint/DOMPoint)
4.  Properties
    1.  [`w`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPoint/w)
    2.  [`x`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPoint/x)
    3.  [`y`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPoint/y)
    4.  [`z`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPoint/z)
5.  Methods
    1.  [`fromPoint()`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPoint/fromPoint)
6.  Inheritance:
    1.  [`DOMPointReadOnly`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPointReadOnly)
7.  Related pages for DOM
    1.  [`AbortController`](https://developer.mozilla.org/en-US/docs/Web/API/AbortController)
    2.  [`AbortSignal`](https://developer.mozilla.org/en-US/docs/Web/API/AbortSignal)
    3.  [`AbstractRange`](https://developer.mozilla.org/en-US/docs/Web/API/AbstractRange)
    4.  [`Attr`](https://developer.mozilla.org/en-US/docs/Web/API/Attr)
    5.  [`ByteString`](https://developer.mozilla.org/en-US/docs/Web/API/ByteString)
    6.  [`CDATASection`](https://developer.mozilla.org/en-US/docs/Web/API/CDATASection)
    7.  [`CSSPrimitiveValue`](https://developer.mozilla.org/en-US/docs/Web/API/CSSPrimitiveValue)
    8.  [`CSSValue`](https://developer.mozilla.org/en-US/docs/Web/API/CSSValue)
    9.  [`CSSValueList`](https://developer.mozilla.org/en-US/docs/Web/API/CSSValueList)
    10. [`CharacterData`](https://developer.mozilla.org/en-US/docs/Web/API/CharacterData)
    11. [`ChildNode`](https://developer.mozilla.org/en-US/docs/Web/API/ChildNode)
    12. [`Comment`](https://developer.mozilla.org/en-US/docs/Web/API/Comment)
    13. [`CustomEvent`](https://developer.mozilla.org/en-US/docs/Web/API/CustomEvent)
    14. [`DOMConfiguration`](https://developer.mozilla.org/en-US/docs/Web/API/DOMConfiguration)
    15. [`DOMError`](https://developer.mozilla.org/en-US/docs/Web/API/DOMError)
    16. [`DOMErrorHandler`](https://developer.mozilla.org/en-US/docs/Web/API/DOMErrorHandler)
    17. [`DOMException`](https://developer.mozilla.org/en-US/docs/Web/API/DOMException)
    18. [`DOMImplementation`](https://developer.mozilla.org/en-US/docs/Web/API/DOMImplementation)
    19. [`DOMImplementationList`](https://developer.mozilla.org/en-US/docs/Web/API/DOMImplementationList)
    20. [`DOMImplementationRegistry`](https://developer.mozilla.org/en-US/docs/Web/API/DOMImplementationRegistry)
    21. [`DOMImplementationSource`](https://developer.mozilla.org/en-US/docs/Web/API/DOMImplementationSource)
    22. [`DOMLocator`](https://developer.mozilla.org/en-US/docs/Web/API/DOMLocator)
    23. [`DOMObject`](https://developer.mozilla.org/en-US/docs/Web/API/DOMObject)
    24. [`DOMParser`](https://developer.mozilla.org/en-US/docs/Web/API/DOMParser)
    25. [`DOMPointInit`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPointInit)
    26. [`DOMPointReadOnly`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPointReadOnly)
    27. [`DOMRect`](https://developer.mozilla.org/en-US/docs/Web/API/DOMRect)
    28. [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString)
    29. [`DOMTimeStamp`](https://developer.mozilla.org/en-US/docs/Web/API/DOMTimeStamp)
    30. [`DOMTokenList`](https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList)
    31. [`DOMUserData`](https://developer.mozilla.org/en-US/docs/Web/API/DOMUserData)
    32. [`Document`](https://developer.mozilla.org/en-US/docs/Web/API/Document)
    33. [`DocumentFragment`](https://developer.mozilla.org/en-US/docs/Web/API/DocumentFragment)
    34. [`DocumentType`](https://developer.mozilla.org/en-US/docs/Web/API/DocumentType)
    35. [`Element`](https://developer.mozilla.org/en-US/docs/Web/API/Element)
    36. [`ElementTraversal`](https://developer.mozilla.org/en-US/docs/Web/API/ElementTraversal)
    37. [`Entity`](https://developer.mozilla.org/en-US/docs/Web/API/Entity)
    38. [`EntityReference`](https://developer.mozilla.org/en-US/docs/Web/API/EntityReference)
    39. [`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event)
    40. [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)
    41. [`HTMLCollection`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCollection)
    42. [`MutationObserver`](https://developer.mozilla.org/en-US/docs/Web/API/MutationObserver)
    43. [`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node)
    44. [`NodeFilter`](https://developer.mozilla.org/en-US/docs/Web/API/NodeFilter)
    45. [`NodeIterator`](https://developer.mozilla.org/en-US/docs/Web/API/NodeIterator)
    46. [`NodeList`](https://developer.mozilla.org/en-US/docs/Web/API/NodeList)
    47. [`ProcessingInstruction`](https://developer.mozilla.org/en-US/docs/Web/API/ProcessingInstruction)
    48. [`PromiseResolver`](https://developer.mozilla.org/en-US/docs/Web/API/PromiseResolver)
    49. [`Range`](https://developer.mozilla.org/en-US/docs/Web/API/Range)
    50. [`StaticRange`](https://developer.mozilla.org/en-US/docs/Web/API/StaticRange)
    51. [`Text`](https://developer.mozilla.org/en-US/docs/Web/API/Text)
    52. [`TextDecoder`](https://developer.mozilla.org/en-US/docs/Web/API/TextDecoder)
    53. [`TextEncoder`](https://developer.mozilla.org/en-US/docs/Web/API/TextEncoder)
    54. [`TimeRanges`](https://developer.mozilla.org/en-US/docs/Web/API/TimeRanges)
    55. [`TreeWalker`](https://developer.mozilla.org/en-US/docs/Web/API/TreeWalker)
    56. [`TypeInfo`](https://developer.mozilla.org/en-US/docs/Web/API/TypeInfo)
    57. [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString)
    58. [`UserDataHandler`](https://developer.mozilla.org/en-US/docs/Web/API/UserDataHandler)
    59. [`XMLDocument`](https://developer.mozilla.org/en-US/docs/Web/API/XMLDocument)

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
