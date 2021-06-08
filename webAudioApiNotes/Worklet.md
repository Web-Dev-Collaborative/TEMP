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
3.  <a href="Worklet.html" class="breadcrumb-current-page"><span data-property="name">Worklet</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Worklet types](#worklet_types)
-   [Properties](#properties)
-   [Methods](#methods)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

Worklet
=======

#### Experimental

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

<span class="seoSummary">The **`Worklet`** interface is a lightweight version of [`Web Workers`](Worker.html "Web Workers") and gives developers access to low-level parts of the rendering pipeline.</span> With Worklets, you can run JavaScript and [WebAssembly](https://developer.mozilla.org/en-US/docs/WebAssembly) code to do graphics rendering or audio processing where high performance is required.

[Worklet types](#worklet_types "Permalink to Worklet types")
------------------------------------------------------------

Worklets are restricted to specific use cases; they cannot be used for arbitrary computations like Web Workers. The `Worklet` interface abstracts properties and methods common to all kind of worklets, and cannot be created directly. Instead, you can use one of the following classes:

<table><colgroup><col style="width: 25%" /><col style="width: 25%" /><col style="width: 25%" /><col style="width: 25%" /></colgroup><thead><tr class="header"><th>Name</th><th>Description</th><th>Location</th><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="PaintWorklet.html"><code>PaintWorklet</code></a></td><td><p>For programmatically generating an image where a CSS property expects a file. Access this interface through <a href="CSS/paintWorklet.html"><code>CSS.paintWorklet</code></a>.</p></td><td><strong>Chrome:</strong> Main thread<br />
<strong>Gecko:</strong> Paint thread</td><td><a href="https://drafts.css-houdini.org/css-paint-api-1/#paint-worklet" class="external">CSS Painting API</a></td></tr><tr class="even"><td><a href="AudioWorklet.html"><code>AudioWorklet</code></a></td><td>For audio processing with custom AudioNodes.</td><td>Web Audio render thread</td><td><a href="https://webaudio.github.io/web-audio-api/#AudioWorklet" class="external">Web Audio API</a></td></tr><tr class="odd"><td><span class="page-not-created"><code>AnimationWorklet</code></span></td><td>For creating scroll-linked and other high performance procedural animations.</td><td>Compositor thread</td><td><a href="https://wicg.github.io/animation-worklet/" class="external">CSS Animation Worklet API</a></td></tr><tr class="even"><td><span class="page-not-created"><code>LayoutWorklet</code></span></td><td>For defining the positioning and dimensions of custom elements.</td><td></td><td><a href="https://drafts.css-houdini.org/css-layout-api-1/#layout-worklet" class="external">CSS Layout API</a></td></tr></tbody></table>

For 3D rendering with [WebGL](WebGL_API.html), you don't use Worklets. Instead, you write Vertex Shaders and Fragment Shaders using GLSL code, and those shaders will then run on the graphics card.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

*The Worklet interface does not define any properties.*

[Methods](#methods "Permalink to Methods")
------------------------------------------

[`Worklet.addModule()`](Worklet/addModule.html)   
Adds the script module at the given URL to the current worklet.

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#worklets-worklet" class="external">HTML Living Standard<br />
<span class="small">The definition of 'Worklet' in that specification.</span></a></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   <a href="https://developers.google.com/web/updates/2016/05/houdini" class="external">Houdini: Demystifying CSS</a> on Google Developers (May 2016)
-   <a href="https://www.youtube.com/watch?v=g1L4O1smMC0&amp;t=1m33s" class="external">AudioWorklet :: What, Why, and How</a> on YouTube (November 2017)
-   <a href="https://developers.google.com/web/updates/2017/12/audio-worklet" class="external">Enter AudioWorklet</a> on Google Developers (December 2017)
-   <a href="https://www.youtube.com/watch?v=ZPkMMShYxKU&amp;t=0m19s" class="external">Animation Worklet - HTTP203 Advent</a> on YouTube (December 2017)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/worklet/index.html "Folder: en-us/web/api/worklet (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWorklet%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fworklet%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWorklet%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fworklet%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F94c536f9b3a50303a85e7963a4ff4958d1aec382%0A*+Document+last+modified%3A+2021-05-31T17%3A13%3A02.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22Worklet%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](Worklet/contributors.txt)

Change your languageSelect your preferred language English (US)日本語

Change language

#### Related Topics

1.  **[`Worklet`](Worklet.html)**
2.  Methods
    1.  [`addModule()`](Worklet/addModule.html)

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
