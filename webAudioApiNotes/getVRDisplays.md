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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/Navigator" class="breadcrumb-penultimate"><span data-property="name">Navigator</span></a>
4.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/Navigator/getVRDisplays" class="breadcrumb-current-page"><span data-property="name">Navigator.getVRDisplays()</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Syntax](#syntax)
-   [Examples](#examples)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

Navigator.getVRDisplays()
=========================

#### Deprecated

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The **`getVRDisplays()`** method of the [`Navigator`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator) interface returns a promise that resolves to an array of [`VRDisplay`](https://developer.mozilla.org/en-US/docs/Web/API/VRDisplay) objects representing any available VR displays connected to the computer.

[Syntax](#syntax "Permalink to Syntax")
---------------------------------------

    navigator.getVRDisplays().then(function(displays) {
      // Do something with the available VR displays
    });

### [Parameters](#parameters "Permalink to Parameters")

None.

### [Return value](#return_value "Permalink to Return value")

A promise that resolves to an array of [`VRDisplay`](https://developer.mozilla.org/en-US/docs/Web/API/VRDisplay) objects.

[Examples](#examples "Permalink to Examples")
---------------------------------------------

    if(navigator.getVRDisplays) {
      console.log('WebVR 1.1 supported');
      // Then get the displays attached to the computer
      navigator.getVRDisplays().then(function(displays) {
        // If a display is available, use it to present the scene
        if(displays.length > 0) {
          vrDisplay = displays[0];
          // Now we have our VRDisplay object and can do what we want with it
        }
      });
    }

**Note**: You can see this complete code at <a href="https://github.com/mdn/webvr-tests/blob/master/raw-webgl-example/webgl-demo.js" class="external">raw-webgl-example</a>.

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webvr/spec/1.1/#navigator-getvrdisplays-attribute" class="external">WebVR 1.1<br />
<span class="small">The definition of 'getVRDisplays()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [WebVR API homepage](https://developer.mozilla.org/en-US/docs/Web/API/WebVR_API)
-   <a href="https://mixedreality.mozilla.org/" class="external">https://mixedreality.mozilla.org/</a> — demos, downloads, and other resources from the Mozilla VR team.

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/navigator/getvrdisplays/index.html "Folder: en-us/web/api/navigator/getvrdisplays (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FNavigator%2FgetVRDisplays%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fnavigator%2Fgetvrdisplays%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FNavigator%2FgetVRDisplays%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fnavigator%2Fgetvrdisplays%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F9b648e559239b3e682abfcb15845a954d420b207%0A*+Document+last+modified%3A+2021-05-31T17%3A00%3A38.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22Navigator.getVRDisplays%28%29%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/getVRDisplays/contributors.txt)

Change your languageSelect your preferred language English (US)日本語Русский

Change language

#### Related Topics

1.  **[WebVR API](https://developer.mozilla.org/en-US/docs/Web/API/WebVR_API)**
2.  Guides
    1.  [Using the WebVR API](https://developer.mozilla.org/en-US/docs/Web/API/WebVR_API/Using_the_WebVR_API)
    2.  [WebVR concepts](https://developer.mozilla.org/en-US/docs/Web/API/WebVR_API/Concepts)
    3.  [Using VR controllers with WebVR](https://developer.mozilla.org/en-US/docs/Web/API/WebVR_API/Using_VR_controllers_with_WebVR)
3.  Interfaces
    1.  [`VRDisplay`](https://developer.mozilla.org/en-US/docs/Web/API/VRDisplay)
    2.  [`VRDisplayCapabilities`](https://developer.mozilla.org/en-US/docs/Web/API/VRDisplayCapabilities)
    3.  [`VRDisplayEvent`](https://developer.mozilla.org/en-US/docs/Web/API/VRDisplayEvent)
    4.  [`VRFrameData`](https://developer.mozilla.org/en-US/docs/Web/API/VRFrameData)
    5.  [`VRPose`](https://developer.mozilla.org/en-US/docs/Web/API/VRPose)
    6.  [`VREyeParameters`](https://developer.mozilla.org/en-US/docs/Web/API/VREyeParameters)
    7.  [`VRFieldOfView`](https://developer.mozilla.org/en-US/docs/Web/API/VRFieldOfView)
    8.  [`VRLayerInit`](https://developer.mozilla.org/en-US/docs/Web/API/VRLayerInit)
    9.  [`VRStageParameters`](https://developer.mozilla.org/en-US/docs/Web/API/VRStageParameters)
4.  Properties
    1.  [`Gamepad.displayId`](https://developer.mozilla.org/en-US/docs/Web/API/Gamepad/displayId)
    2.  [`Navigator.activeVRDisplays`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/activeVRDisplays)
5.  Methods
    1.  [`Navigator.getVRDisplays()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/getVRDisplays)
6.  Events
    1.  [`Window`: `vrdisplayactivate`](https://developer.mozilla.org/en-US/docs/Web/API/Window/vrdisplayactivate_event)
    2.  [`Window`: `vrdisplayblur`](https://developer.mozilla.org/en-US/docs/Web/API/Window/vrdisplayblur_event)
    3.  [`Window`: `vrdisplayconnected`](https://developer.mozilla.org/en-US/docs/Web/API/Window/vrdisplayconnected_event)
    4.  [`Window`: `vrdisplaydeactivate`](https://developer.mozilla.org/en-US/docs/Web/API/Window/vrdisplaydeactivate_event)
    5.  [`Window`: `vrdisplaydisconnected`](https://developer.mozilla.org/en-US/docs/Web/API/Window/vrdisplaydisconnected_event)
    6.  [`Window`: `vrdisplayfocus`](https://developer.mozilla.org/en-US/docs/Web/API/Window/vrdisplayfocus_event)
    7.  [`Window`: `vrdisplaypresentchange`](https://developer.mozilla.org/en-US/docs/Web/API/Window/vrdisplaypresentchange_event)

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
