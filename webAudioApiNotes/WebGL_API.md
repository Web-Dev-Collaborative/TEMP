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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API" class="breadcrumb-current-page"><span data-property="name">WebGL: 2D and 3D graphics for the web</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Reference](#reference)
-   [Guides and tutorials](#guides_and_tutorials)
-   [Resources](#resources)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

WebGL: 2D and 3D graphics for the web
=====================================

<span class="seoSummary">WebGL (Web Graphics Library) is a JavaScript API for rendering high-performance interactive 3D and 2D graphics within any compatible web browser without the use of plug-ins. WebGL does so by introducing an API that closely conforms to OpenGL ES 2.0 that can be used in HTML5 [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) elements.</span> This conformance makes it possible for the API to take advantage of hardware graphics acceleration provided by the user's device.

Support for WebGL is present in [Firefox](https://developer.mozilla.org/en-US/docs/Mozilla/Firefox "Firefox 4 for developers") 4+, <a href="https://www.google.com/chrome/" class="external">Google Chrome</a> 9+, <a href="https://www.opera.com/" class="external">Opera</a> 12+, <a href="https://www.apple.com/safari/" class="external">Safari</a> 5.1+, <a href="https://windows.microsoft.com/en-us/internet-explorer/browser-ie" class="external">Internet Explorer</a> 11+, and <a href="https://www.microsoft.com/en-us/edge" class="external">Microsoft Edge</a> build 10240+; however, the user's device must also have hardware that supports these features.

The [WebGL 2](#webgl_2) API introduces support for much of the OpenGL ES 3.0 feature set; it's provided through the [`WebGL2RenderingContext`](https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext) interface.

The [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element is also used by the [Canvas API](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API) to do 2D graphics on web pages.

[Reference](#reference "Permalink to Reference")
------------------------------------------------

### [Standard interfaces](#standard_interfaces "Permalink to Standard interfaces")

-   [`WebGLRenderingContext`](https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext)
-   [`WebGL2RenderingContext`](https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext)
-   [`WebGLActiveInfo`](https://developer.mozilla.org/en-US/docs/Web/API/WebGLActiveInfo)
-   [`WebGLBuffer`](https://developer.mozilla.org/en-US/docs/Web/API/WebGLBuffer)
-   [`WebGLContextEvent`](https://developer.mozilla.org/en-US/docs/Web/API/WebGLContextEvent)
-   [`WebGLFramebuffer`](https://developer.mozilla.org/en-US/docs/Web/API/WebGLFramebuffer)
-   [`WebGLProgram`](https://developer.mozilla.org/en-US/docs/Web/API/WebGLProgram)
-   [`WebGLQuery`](https://developer.mozilla.org/en-US/docs/Web/API/WebGLQuery)
-   [`WebGLRenderbuffer`](https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderbuffer)
-   [`WebGLSampler`](https://developer.mozilla.org/en-US/docs/Web/API/WebGLSampler)
-   [`WebGLShader`](https://developer.mozilla.org/en-US/docs/Web/API/WebGLShader)
-   [`WebGLShaderPrecisionFormat`](https://developer.mozilla.org/en-US/docs/Web/API/WebGLShaderPrecisionFormat)
-   [`WebGLSync`](https://developer.mozilla.org/en-US/docs/Web/API/WebGLSync)
-   [`WebGLTexture`](https://developer.mozilla.org/en-US/docs/Web/API/WebGLTexture)
-   [`WebGLTransformFeedback`](https://developer.mozilla.org/en-US/docs/Web/API/WebGLTransformFeedback)
-   [`WebGLUniformLocation`](https://developer.mozilla.org/en-US/docs/Web/API/WebGLUniformLocation)
-   [`WebGLVertexArrayObject`](https://developer.mozilla.org/en-US/docs/Web/API/WebGLVertexArrayObject)

### [Extensions](#extensions "Permalink to Extensions")

-   [`ANGLE_instanced_arrays`](https://developer.mozilla.org/en-US/docs/Web/API/ANGLE_instanced_arrays)
-   [`EXT_blend_minmax`](https://developer.mozilla.org/en-US/docs/Web/API/EXT_blend_minmax)
-   [`EXT_color_buffer_float`](https://developer.mozilla.org/en-US/docs/Web/API/EXT_color_buffer_float)
-   [`EXT_color_buffer_half_float`](https://developer.mozilla.org/en-US/docs/Web/API/EXT_color_buffer_half_float)
-   [`EXT_disjoint_timer_query`](https://developer.mozilla.org/en-US/docs/Web/API/EXT_disjoint_timer_query)
-   [`EXT_float_blend`](https://developer.mozilla.org/en-US/docs/Web/API/EXT_float_blend)
-   [`EXT_frag_depth`](https://developer.mozilla.org/en-US/docs/Web/API/EXT_frag_depth)
-   [`EXT_shader_texture_lod`](https://developer.mozilla.org/en-US/docs/Web/API/EXT_shader_texture_lod)
-   [`EXT_sRGB`](https://developer.mozilla.org/en-US/docs/Web/API/EXT_sRGB)
-   [`EXT_texture_compression_bptc`](https://developer.mozilla.org/en-US/docs/Web/API/EXT_texture_compression_bptc)
-   [`EXT_texture_compression_rgtc`](https://developer.mozilla.org/en-US/docs/Web/API/EXT_texture_compression_rgtc)
-   [`EXT_texture_filter_anisotropic`](https://developer.mozilla.org/en-US/docs/Web/API/EXT_texture_filter_anisotropic)
-   [`EXT_texture_norm16`](https://developer.mozilla.org/en-US/docs/Web/API/EXT_texture_norm16)
-   [`KHR_parallel_shader_compile`](https://developer.mozilla.org/en-US/docs/Web/API/KHR_parallel_shader_compile)
-   [`OES_element_index_uint`](https://developer.mozilla.org/en-US/docs/Web/API/OES_element_index_uint)
-   [`OES_fbo_render_mipmap`](https://developer.mozilla.org/en-US/docs/Web/API/OES_fbo_render_mipmap)
-   [`OES_standard_derivatives`](https://developer.mozilla.org/en-US/docs/Web/API/OES_standard_derivatives)
-   [`OES_texture_float`](https://developer.mozilla.org/en-US/docs/Web/API/OES_texture_float)
-   [`OES_texture_float_linear`](https://developer.mozilla.org/en-US/docs/Web/API/OES_texture_float_linear)
-   [`OES_texture_half_float`](https://developer.mozilla.org/en-US/docs/Web/API/OES_texture_half_float)
-   [`OES_texture_half_float_linear`](https://developer.mozilla.org/en-US/docs/Web/API/OES_texture_half_float_linear)
-   [`OES_vertex_array_object`](https://developer.mozilla.org/en-US/docs/Web/API/OES_vertex_array_object)
-   [`OVR_multiview2`](https://developer.mozilla.org/en-US/docs/Web/API/OVR_multiview2)
-   [`WEBGL_color_buffer_float`](https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_color_buffer_float)
-   [`WEBGL_compressed_texture_astc`](https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_compressed_texture_astc)
-   [`WEBGL_compressed_texture_atc`](https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_compressed_texture_atc)
-   [`WEBGL_compressed_texture_etc`](https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_compressed_texture_etc)
-   [`WEBGL_compressed_texture_etc1`](https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_compressed_texture_etc1)
-   [`WEBGL_compressed_texture_pvrtc`](https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_compressed_texture_pvrtc)
-   [`WEBGL_compressed_texture_s3tc`](https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_compressed_texture_s3tc)
-   [`WEBGL_compressed_texture_s3tc_srgb`](https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_compressed_texture_s3tc_srgb)
-   [`WEBGL_debug_renderer_info`](https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_debug_renderer_info)
-   [`WEBGL_debug_shaders`](https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_debug_shaders)
-   [`WEBGL_depth_texture`](https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_depth_texture)
-   [`WEBGL_draw_buffers`](https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_draw_buffers)
-   [`WEBGL_lose_context`](https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_lose_context)
-   [`WEBGL_multi_draw`](https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_multi_draw)

### [Events](#events "Permalink to Events")

-   [`webglcontextlost`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/webglcontextlost_event "webglcontextlost")
-   [`webglcontextrestored`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/webglcontextrestored_event "webglcontextrestored")
-   [`webglcontextcreationerror`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/webglcontextcreationerror_event "webglcontextcreationerror")

### [Constants and types](#constants_and_types "Permalink to Constants and types")

-   [WebGL constants](https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/Constants)
-   [WebGL types](https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/Types)

### [WebGL 2](#webgl_2 "Permalink to WebGL 2")

WebGL 2 is a major update to WebGL which is provided through the [`WebGL2RenderingContext`](https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext) interface. It is based on OpenGL ES 3.0 and new features include:

-   [3D textures](https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/texImage3D),
-   [Sampler objects](https://developer.mozilla.org/en-US/docs/Web/API/WebGLSampler),
-   [Uniform Buffer objects](https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext#uniform_buffer_objects),
-   [Sync objects](https://developer.mozilla.org/en-US/docs/Web/API/WebGLSync),
-   [Query objects](https://developer.mozilla.org/en-US/docs/Web/API/WebGLQuery),
-   [Transform Feedback objects](https://developer.mozilla.org/en-US/docs/Web/API/WebGLTransformFeedback),
-   Promoted extensions that are now core to WebGL 2: [Vertex Array objects](https://developer.mozilla.org/en-US/docs/Web/API/WebGLVertexArrayObject), [instancing](https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/drawArraysInstanced), [multiple render targets](https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/drawBuffers), [fragment depth](https://developer.mozilla.org/en-US/docs/Web/API/EXT_frag_depth).

See also the blog post <a href="https://hacks.mozilla.org/2017/01/webgl-2-lands-in-firefox/" class="external">"WebGL 2 lands in Firefox"</a> and <a href="https://webglsamples.org/WebGL2Samples/" class="external">webglsamples.org/WebGL2Samples</a> for a few demos.

[Guides and tutorials](#guides_and_tutorials "Permalink to Guides and tutorials")
---------------------------------------------------------------------------------

Below, you'll find an assortment of guides to help you learn WebGL concepts and tutorials that offer step-by-step lessons and examples.

### [Guides](#guides "Permalink to Guides")

[Data in WebGL](https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/Data)  
A guide to variables, buffers, and other types of data used when writing WebGL code.

[WebGL best practices](https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/WebGL_best_practices)  
Tips and suggestions to help you improve the quality, performance, and reliability of your WebGL content.

[Using extensions](https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/Using_Extensions)  
A guide to using WebGL extensions.

### [Tutorials](#tutorials "Permalink to Tutorials")

[WebGL tutorial](https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/Tutorial)  
A beginner's guide to WebGL core concepts. A good place to start if you don't have previous WebGL experience.

### [Examples](#examples "Permalink to Examples")

[A basic 2D WebGL animation example](https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/Basic_2D_animation_example)  
This example demonstrates the simple animation of a one-color shape. Topics examined are adapting to aspect ratio differences, a function to build shader programs from sets of multiple shaders, and the basics of drawing in WebGL.

[WebGL by example](https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/By_example)  
A series of live samples with short explanations that showcase WebGL concepts and capabilities. The examples are sorted according to topic and level of difficulty, covering the WebGL rendering context, shader programming, textures, geometry, user interaction, and more.

### [Advanced tutorials](#advanced_tutorials "Permalink to Advanced tutorials")

[WebGL model view projection](https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/WebGL_model_view_projection)  
A detailed explanation of the three core matrices that are typically used to represent a 3D object view: the model, view and projection matrices.

[Matrix math for the web](https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/Matrix_math_for_the_web)  
A useful guide to how 3D transform matrices work, and can be used on the web — both for WebGL calculations and in CSS3 transforms.

[Resources](#resources "Permalink to Resources")
------------------------------------------------

-   <a href="https://www.khronos.org/webgl/" class="external">Khronos WebGL site</a> The main web site for WebGL at the Khronos Group.
-   <a href="https://www.html5rocks.com/en/tutorials/webgl/webgl_fundamentals/" class="external">WebGL Fundamentals</a> A basic tutorial with fundamentals of WebGL.
-   <a href="https://www.youtube.com/embed/H4c8t6myAWU/?feature=player_detailpage" class="external">Raw WebGL: An introduction to WebGL</a> A talk by Nick Desaulniers that introduces the basics of WebGL.
-   <a href="http://webglplayground.net/" class="external">WebGL playground</a> An online tool for creating and sharing WebGL projects. Good for quick prototyping and experimenting.
-   <a href="http://www.webglacademy.com/" class="external">WebGL Academy</a> An HTML/JavaScript editor with tutorials to learn basics of webgl programming.
-   <a href="http://webglstats.com/" class="external">WebGL Stats</a> A site with statistics about WebGL capabilities in browsers on different platforms.

### [Libraries](#libraries "Permalink to Libraries")

-   <a href="https://threejs.org/" class="external">three.js</a> is an open-source, fully featured 3D WebGL library.
-   <a href="https://www.babylonjs.com/" class="external">Babylon.js</a> is a powerful, simple, and open game and 3D rendering engine packed into a friendly JavaScript framework.
-   <a href="https://www.pixijs.com/" class="external">Pixi.js</a> is a fast, open-source 2D WebGL renderer.
-   <a href="https://phaser.io/" class="external">Phaser</a> is a fast, free and fun open source framework for Canvas and WebGL powered browser games.
-   <a href="https://playcanvas.com/" class="external">PlayCanvas</a> is an open-source game engine.
-   <a href="https://github.com/toji/gl-matrix" class="link-https external">glMatrix</a> is a JavaScript matrix and vector library for high-performance WebGL apps.
-   <a href="https://twgljs.org/" class="external">twgl</a> is a library for making webgl less verbose.
-   <a href="https://github.com/redcamel/RedGL2" class="external">RedGL</a> is an open-source 3D WebGL library.
-   <a href="https://kitware.github.io/vtk-js/" class="external">vtk.js</a> is a JavaScript library for scientific visualization in your browser.
-   <a href="https://greggman.github.io/webgl-lint/" class="external">webgl-lint</a> will help find errors in your WebGL code and provide useful info

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/" class="external" title="The &#39;OpenGL ES 3.0&#39; specification">OpenGL ES 3.0</a></td><td><span class="spec-standard">Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/" class="external" title="The &#39;OpenGL ES 2.0&#39; specification">OpenGL ES 2.0</a></td><td><span class="spec-standard">Standard</span></td><td></td></tr><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/" class="external" title="The &#39;WebGL 2.0&#39; specification">WebGL 2.0</a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Builds on top of WebGL 1. Based on OpenGL ES 3.0.</td></tr><tr class="even"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/" class="external" title="The &#39;WebGL 1.0&#39; specification">WebGL 1.0</a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition. Based on OpenGL ES 2.0</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

### [WebGL 1](#webgl_1 "Permalink to WebGL 1")

BCD tables only load in the browser

### [WebGL 2](#webgl_2_2 "Permalink to WebGL 2")

BCD tables only load in the browser

### [Compatibility notes](#compatibility_notes "Permalink to Compatibility notes")

In addition to the browser, the GPU itself also needs to support the feature. So, for example, S3 Texture Compression (S3TC) is only available on Tegra-based tablets. Most browsers make the WebGL context available through the `webgl` context name, but older ones need `experimental-webgl` as well. In addition, the upcoming [WebGL 2](https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext) is fully backwards-compatible and will have the context name `webgl2`.

### [Gecko notes](#gecko_notes "Permalink to Gecko notes")

#### WebGL debugging and testing

Starting with Gecko 10.0 (Firefox 10.0 / Thunderbird 10.0 / SeaMonkey 2.7), there are two preferences available which let you control the capabilities of WebGL for testing purposes:

`webgl.min_capability_mode`  
A Boolean property that, when `true`, enables a minimum capability mode. When in this mode, WebGL is configured to only support the bare minimum feature set and capabilities required by the WebGL specification. This lets you ensure that your WebGL code will work on any device or browser, regardless of their capabilities. This is `false` by default.

`webgl.disable_extensions`  
A Boolean property that, when `true`, disables all WebGL extensions. This is `false` by default.

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Canvas API](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API)
-   [Compatibility info about WebGL extensions](https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/getSupportedExtensions#browser_compatibility)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/webgl_api/index.html "Folder: en-us/web/api/webgl_api (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWebGL_API%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fwebgl_api%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWebGL_API%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fwebgl_api%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F43c2267c237b1c0bb7b3f5c70b7ac9146ff48c7d%0A*+Document+last+modified%3A+2021-05-27T18%3A46%3A01.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22WebGL%3A+2D+and+3D+graphics+for+the+web%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 27, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/contributors.txt)

Change your languageSelect your preferred language English (US)DeutschEspañolFrançais日本語한국어PolskiPortuguês (do Brasil)Русский中文 (简体)正體中文 (繁體)

Change language

#### Related Topics

1.  [**WebGL API**](https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API)
2.  WebGL tutorial
    1.  [Getting started with WebGL](https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/Tutorial/Getting_started_with_WebGL)
    2.  [Adding 2D content to a WebGL context](https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/Tutorial/Adding_2D_content_to_a_WebGL_context)
    3.  [Using shaders to apply color in WebGL](https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/Tutorial/Using_shaders_to_apply_color_in_WebGL)
    4.  [Animating objects with WebGL](https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/Tutorial/Animating_objects_with_WebGL)
    5.  [Creating 3D objects using WebGL](https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/Tutorial/Creating_3D_objects_using_WebGL)
    6.  [Using textures in WebGL](https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/Tutorial/Using_textures_in_WebGL)
    7.  [Lighting in WebGL](https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/Tutorial/Lighting_in_WebGL)
    8.  [Animating textures in WebGL](https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/Tutorial/Animating_textures_in_WebGL)
3.  Examples and articles
    1.  [Matrix math for the web](https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/Matrix_math_for_the_web)
    2.  [WebGL model view projection](https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/WebGL_model_view_projection)
    3.  [WebGL best practices](https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/WebGL_best_practices)
    4.  [Using WebGL extensions](https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/Using_Extensions)
    5.  [A basic 2D WebGL animation example](https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/Basic_2D_animation_example)
    6.  [WebGL by example](https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/By_example)
4.  Interfaces
    1.  [`WebGLRenderingContext`](https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext)
    2.  [`WebGL2RenderingContext`](https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext)
    3.  [`WebGLActiveInfo`](https://developer.mozilla.org/en-US/docs/Web/API/WebGLActiveInfo)
    4.  [`WebGLBuffer`](https://developer.mozilla.org/en-US/docs/Web/API/WebGLBuffer)
    5.  [`WebGLContextEvent`](https://developer.mozilla.org/en-US/docs/Web/API/WebGLContextEvent)
    6.  [`WebGLFramebuffer`](https://developer.mozilla.org/en-US/docs/Web/API/WebGLFramebuffer)
    7.  [`WebGLProgram`](https://developer.mozilla.org/en-US/docs/Web/API/WebGLProgram)
    8.  [`WebGLQuery`](https://developer.mozilla.org/en-US/docs/Web/API/WebGLQuery)
    9.  [`WebGLRenderbuffer`](https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderbuffer)
    10. [`WebGLSampler`](https://developer.mozilla.org/en-US/docs/Web/API/WebGLSampler)
    11. [`WebGLShader`](https://developer.mozilla.org/en-US/docs/Web/API/WebGLShader)
    12. [`WebGLShaderPrecisionFormat`](https://developer.mozilla.org/en-US/docs/Web/API/WebGLShaderPrecisionFormat)
    13. [`WebGLSync`](https://developer.mozilla.org/en-US/docs/Web/API/WebGLSync)
    14. [`WebGLTexture`](https://developer.mozilla.org/en-US/docs/Web/API/WebGLTexture)
    15. [`WebGLTransformFeedback`](https://developer.mozilla.org/en-US/docs/Web/API/WebGLTransformFeedback)
    16. [`WebGLUniformLocation`](https://developer.mozilla.org/en-US/docs/Web/API/WebGLUniformLocation)
    17. [`WebGLVertexArrayObject`](https://developer.mozilla.org/en-US/docs/Web/API/WebGLVertexArrayObject)
5.  **[Documentation:](https://developer.mozilla.org/en-US/docs/MDN)**
6.  Contribute
    1.  [The MDN project](https://developer.mozilla.org/en-US/docs/MDN)

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
