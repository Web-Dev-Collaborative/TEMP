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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/Window" class="breadcrumb-penultimate"><span data-property="name">Window</span></a>
4.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/load_event" class="breadcrumb-current-page"><span data-property="name">Window: load event</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Examples](#examples)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

Window: load event
==================

The **`load`** event is fired when the whole page has loaded, including all dependent resources such as stylesheets and images. This is in contrast to [`DOMContentLoaded`](https://developer.mozilla.org/en-US/docs/Web/API/Document/DOMContentLoaded_event "DOMContentLoaded"), which is fired as soon as the page DOM has been loaded, without waiting for resources to finish loading.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/Event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onload" title="onload"><code>onload</code></a></td></tr></tbody></table>

[Examples](#examples "Permalink to Examples")
---------------------------------------------

Log a message when the page is fully loaded:

    window.addEventListener('load', (event) => {
      console.log('page is fully loaded');
    });

The same, but using the `onload` event handler property:

    window.onload = (event) => {
      console.log('page is fully loaded');
    };

### [Live example](#live_example "Permalink to Live example")

#### HTML

    <div class="controls">
      <button id="reload" type="button">Reload</button>
    </div>

    <div class="event-log">
      <label>Event log:</label>
      <textarea readonly class="event-log-contents" rows="8" cols="30"></textarea>
    </div>

#### JS

    const log = document.querySelector('.event-log-contents');
    const reload = document.querySelector('#reload');

    reload.addEventListener('click', () => {
      log.textContent ='';
      window.setTimeout(() => {
          window.location.reload(true);
      }, 200);
    });

    window.addEventListener('load', (event) => {
        log.textContent = log.textContent + 'load\n';
    });

    document.addEventListener('readystatechange', (event) => {
        log.textContent = log.textContent + `readystate: ${document.readyState}\n`;
    });

    document.addEventListener('DOMContentLoaded', (event) => {
        log.textContent = log.textContent + `DOMContentLoaded\n`;
    });

#### Result

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/uievents/#event-type-load" class="external">UI Events<br />
<span class="small">The definition of 'load' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr><tr class="even"><td><a href="https://html.spec.whatwg.org/multipage/#delay-the-load-event" class="external">HTML Living Standard<br />
<span class="small">The definition of 'load event' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>This links to the section in the steps that are carried out at the end of loading a document. 'load' events are fired at many elements too. And note there are many places in the specification that refer to things that can "<a href="https://html.spec.whatwg.org/multipage/parsing.html#delay-the-load-event" class="external">delays the load event</a>".</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   Related events: [`DOMContentLoaded`](https://developer.mozilla.org/en-US/docs/Web/API/Window/DOMContentLoaded_event "DOMContentLoaded"), [`readystatechange`](https://developer.mozilla.org/en-US/docs/Web/API/Document/readystatechange_event "readystatechange"), [`beforeunload`](https://developer.mozilla.org/en-US/docs/Web/API/Window/beforeunload_event "beforeunload"), [`unload`](https://developer.mozilla.org/en-US/docs/Web/API/Window/unload_event "unload")

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/window/load_event/index.html "Folder: en-us/web/api/window/load_event (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWindow%2Fload_event%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fwindow%2Fload_event%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWindow%2Fload_event%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fwindow%2Fload_event%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F94c536f9b3a50303a85e7963a4ff4958d1aec382%0A*+Document+last+modified%3A+2021-05-31T17%3A13%3A02.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22Window%3A+load+event%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/Window/load_event/contributors.txt)

Change your languageSelect your preferred language English (US)DeutschEspañolFrançais日本語한국어Português (do Brasil)Русский中文 (简体)正體中文 (繁體)

Change language

#### Related Topics

1.  **[`Window`](https://developer.mozilla.org/en-US/docs/Web/API/Window)**
2.  Properties
    1.  [`applicationCache`](https://developer.mozilla.org/en-US/docs/Web/API/Window/applicationCache)
    2.  [`caches`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/caches)
    3.  [`closed`](https://developer.mozilla.org/en-US/docs/Web/API/Window/closed)
    4.  [`console`](https://developer.mozilla.org/en-US/docs/Web/API/Window/console)
    5.  [`controllers`](https://developer.mozilla.org/en-US/docs/Web/API/Window/controllers)
    6.  [`crossOriginIsolated`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/crossOriginIsolated)
    7.  [`crypto`](https://developer.mozilla.org/en-US/docs/Web/API/Window/crypto)
    8.  [`customElements`](https://developer.mozilla.org/en-US/docs/Web/API/Window/customElements)
    9.  [`defaultStatus`](https://developer.mozilla.org/en-US/docs/Web/API/Window/defaultStatus)
    10. [`devicePixelRatio`](https://developer.mozilla.org/en-US/docs/Web/API/Window/devicePixelRatio)
    11. [`dialogArguments`](https://developer.mozilla.org/en-US/docs/Web/API/Window/dialogArguments)
    12. [`directories`](https://developer.mozilla.org/en-US/docs/Web/API/Window/directories)
    13. [`document`](https://developer.mozilla.org/en-US/docs/Web/API/Window/document)
    14. [`event`](https://developer.mozilla.org/en-US/docs/Web/API/Window/event)
    15. [`frameElement`](https://developer.mozilla.org/en-US/docs/Web/API/Window/frameElement)
    16. [`frames`](https://developer.mozilla.org/en-US/docs/Web/API/Window/frames)
    17. [`fullScreen`](https://developer.mozilla.org/en-US/docs/Web/API/Window/fullScreen)
    18. [`history`](https://developer.mozilla.org/en-US/docs/Web/API/Window/history)
    19. [`indexedDB`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/indexedDB)
    20. [`innerHeight`](https://developer.mozilla.org/en-US/docs/Web/API/Window/innerHeight)
    21. [`innerWidth`](https://developer.mozilla.org/en-US/docs/Web/API/Window/innerWidth)
    22. [`isSecureContext`](https://developer.mozilla.org/en-US/docs/Web/API/Window/isSecureContext)
    23. [`isSecureContext`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/isSecureContext)
    24. [`length`](https://developer.mozilla.org/en-US/docs/Web/API/Window/length)
    25. [`localStorage`](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage)
    26. [`location`](https://developer.mozilla.org/en-US/docs/Web/API/Window/location)
    27. [`locationbar`](https://developer.mozilla.org/en-US/docs/Web/API/Window/locationbar)
    28. [`menubar`](https://developer.mozilla.org/en-US/docs/Web/API/Window/menubar)
    29. [`mozAnimationStartTime`](https://developer.mozilla.org/en-US/docs/Web/API/Window/mozAnimationStartTime)
    30. [`mozInnerScreenX`](https://developer.mozilla.org/en-US/docs/Web/API/Window/mozInnerScreenX)
    31. [`mozInnerScreenY`](https://developer.mozilla.org/en-US/docs/Web/API/Window/mozInnerScreenY)
    32. [`mozPaintCount`](https://developer.mozilla.org/en-US/docs/Web/API/Window/mozPaintCount)
    33. [`name`](https://developer.mozilla.org/en-US/docs/Web/API/Window/name)
    34. [`navigator`](https://developer.mozilla.org/en-US/docs/Web/API/Window/navigator)
    35. [`onabort`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onabort)
    36. [`onafterprint`](https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onafterprint)
    37. [`onanimationcancel`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onanimationcancel)
    38. [`onanimationend`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onanimationend)
    39. [`onanimationiteration`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onanimationiteration)
    40. [`onappinstalled`](https://developer.mozilla.org/en-US/docs/Web/API/Window/onappinstalled)
    41. [`onauxclick`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onauxclick)
    42. [`onbeforeinstallprompt`](https://developer.mozilla.org/en-US/docs/Web/API/Window/onbeforeinstallprompt)
    43. [`onbeforeprint`](https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onbeforeprint)
    44. [`onbeforeunload`](https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onbeforeunload)
    45. [`onblur`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onblur)
    46. [`oncancel`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oncancel)
    47. [`oncanplay`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oncanplay)
    48. [`oncanplaythrough`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oncanplaythrough)
    49. [`onchange`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onchange)
    50. [`onclick`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onclick)
    51. [`onclose`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onclose)
    52. [`oncontextmenu`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oncontextmenu)
    53. [`oncuechange`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oncuechange)
    54. [`ondblclick`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ondblclick)
    55. [`ondevicemotion`](https://developer.mozilla.org/en-US/docs/Web/API/Window/ondevicemotion)
    56. [`ondeviceorientation`](https://developer.mozilla.org/en-US/docs/Web/API/Window/ondeviceorientation)
    57. [`ondeviceorientationabsolute`](https://developer.mozilla.org/en-US/docs/Web/API/Window/ondeviceorientationabsolute)
    58. [`ondragdrop`](https://developer.mozilla.org/en-US/docs/Web/API/Window/ondragdrop)
    59. [`ondurationchange`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ondurationchange)
    60. [`onended`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onended)
    61. [`onerror`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onerror)
    62. [`onfocus`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onfocus)
    63. [`onformdata`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onformdata)
    64. [`ongamepadconnected`](https://developer.mozilla.org/en-US/docs/Web/API/Window/ongamepadconnected)
    65. [`ongamepaddisconnected`](https://developer.mozilla.org/en-US/docs/Web/API/Window/ongamepaddisconnected)
    66. [`ongotpointercapture`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ongotpointercapture)
    67. [`onhashchange`](https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onhashchange)
    68. [`oninput`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oninput)
    69. [`oninvalid`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oninvalid)
    70. [`onkeydown`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onkeydown)
    71. [`onkeypress`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onkeypress)
    72. [`onkeyup`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onkeyup)
    73. [`onlanguagechange`](https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onlanguagechange)
    74. [`onload`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onload)
    75. [`onloadeddata`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onloadeddata)
    76. [`onloadedmetadata`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onloadedmetadata)
    77. [`onloadend`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onloadend)
    78. [`onloadstart`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onloadstart)
    79. [`onlostpointercapture`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onlostpointercapture)
    80. [`onmessage`](https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onmessage)
    81. [`onmessageerror`](https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onmessageerror)
    82. [`onmousedown`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmousedown)
    83. [`onmouseenter`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmouseenter)
    84. [`onmouseleave`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmouseleave)
    85. [`onmousemove`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmousemove)
    86. [`onmouseout`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmouseout)
    87. [`onmouseover`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmouseover)
    88. [`onmouseup`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmouseup)
    89. [`onmozbeforepaint`](https://developer.mozilla.org/en-US/docs/Web/API/Window/onmozbeforepaint)
    90. [`onpaint`](https://developer.mozilla.org/en-US/docs/Web/API/Window/onpaint)
    91. [`onpause`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpause)
    92. [`onplay`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onplay)
    93. [`onplaying`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onplaying)
    94. [`onpointercancel`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointercancel)
    95. [`onpointerdown`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointerdown)
    96. [`onpointerenter`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointerenter)
    97. [`onpointerleave`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointerleave)
    98. [`onpointermove`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointermove)
    99. [`onpointerout`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointerout)
    100. [`onpointerover`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointerover)
    101. [`onpointerup`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointerup)
    102. [`onpopstate`](https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onpopstate)
    103. [`onrejectionhandled`](https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onrejectionhandled)
    104. [`onreset`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onreset)
    105. [`onresize`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onresize)
    106. [`onscroll`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onscroll)
    107. [`onselect`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onselect)
    108. [`onselectionchange`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onselectionchange)
    109. [`onselectstart`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onselectstart)
    110. [`onstorage`](https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onstorage)
    111. [`onsubmit`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onsubmit)
    112. [`ontouchcancel`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ontouchcancel)
    113. [`ontouchstart`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ontouchstart)
    114. [`ontransitioncancel`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ontransitioncancel)
    115. [`ontransitionend`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ontransitionend)
    116. [`onunhandledrejection`](https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onunhandledrejection)
    117. [`onunload`](https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onunload)
    118. [`onvrdisplayactivate`](https://developer.mozilla.org/en-US/docs/Web/API/Window/onvrdisplayactivate)
    119. [`onvrdisplayblur`](https://developer.mozilla.org/en-US/docs/Web/API/Window/onvrdisplayblur)
    120. [`onvrdisplayconnect`](https://developer.mozilla.org/en-US/docs/Web/API/Window/onvrdisplayconnect)
    121. [`onvrdisplaydeactivate`](https://developer.mozilla.org/en-US/docs/Web/API/Window/onvrdisplaydeactivate)
    122. [`onvrdisplaydisconnect`](https://developer.mozilla.org/en-US/docs/Web/API/Window/onvrdisplaydisconnect)
    123. [`onvrdisplayfocus`](https://developer.mozilla.org/en-US/docs/Web/API/Window/onvrdisplayfocus)
    124. [`onvrdisplaypointerrestricted`](https://developer.mozilla.org/en-US/docs/Web/API/Window/onvrdisplaypointerrestricted)
    125. [`onvrdisplaypointerunrestricted`](https://developer.mozilla.org/en-US/docs/Web/API/Window/onvrdisplaypointerunrestricted)
    126. [`onvrdisplaypresentchange`](https://developer.mozilla.org/en-US/docs/Web/API/Window/onvrdisplaypresentchange)
    127. [`onwheel`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onwheel)
    128. [`opener`](https://developer.mozilla.org/en-US/docs/Web/API/Window/opener)
    129. [`origin`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/origin)
    130. [`outerHeight`](https://developer.mozilla.org/en-US/docs/Web/API/Window/outerHeight)
    131. [`outerWidth`](https://developer.mozilla.org/en-US/docs/Web/API/Window/outerWidth)
    132. [`pageXOffset`](https://developer.mozilla.org/en-US/docs/Web/API/Window/pageXOffset)
    133. [`pageYOffset`](https://developer.mozilla.org/en-US/docs/Web/API/Window/pageYOffset)
    134. [`parent`](https://developer.mozilla.org/en-US/docs/Web/API/Window/parent)
    135. [`performance`](https://developer.mozilla.org/en-US/docs/Web/API/Window/performance)
    136. [`personalbar`](https://developer.mozilla.org/en-US/docs/Web/API/Window/personalbar)
    137. [`pkcs11`](https://developer.mozilla.org/en-US/docs/Web/API/Window/pkcs11)
    138. [`screen`](https://developer.mozilla.org/en-US/docs/Web/API/Window/screen)
    139. [`screenLeft`](https://developer.mozilla.org/en-US/docs/Web/API/Window/screenLeft)
    140. [`screenTop`](https://developer.mozilla.org/en-US/docs/Web/API/Window/screenTop)
    141. [`screenX`](https://developer.mozilla.org/en-US/docs/Web/API/Window/screenX)
    142. [`screenY`](https://developer.mozilla.org/en-US/docs/Web/API/Window/screenY)
    143. [`scrollbars`](https://developer.mozilla.org/en-US/docs/Web/API/Window/scrollbars)
    144. [`scrollMaxX`](https://developer.mozilla.org/en-US/docs/Web/API/Window/scrollMaxX)
    145. [`scrollMaxY`](https://developer.mozilla.org/en-US/docs/Web/API/Window/scrollMaxY)
    146. [`scrollX`](https://developer.mozilla.org/en-US/docs/Web/API/Window/scrollX)
    147. [`scrollY`](https://developer.mozilla.org/en-US/docs/Web/API/Window/scrollY)
    148. [`self`](https://developer.mozilla.org/en-US/docs/Web/API/Window/self)
    149. [`sessionStorage`](https://developer.mozilla.org/en-US/docs/Web/API/Window/sessionStorage)
    150. [`sidebar`](https://developer.mozilla.org/en-US/docs/Web/API/Window/sidebar)
    151. [`speechSynthesis`](https://developer.mozilla.org/en-US/docs/Web/API/Window/speechSynthesis)
    152. [`status`](https://developer.mozilla.org/en-US/docs/Web/API/Window/status)
    153. [`statusbar`](https://developer.mozilla.org/en-US/docs/Web/API/Window/statusbar)
    154. [`toolbar`](https://developer.mozilla.org/en-US/docs/Web/API/Window/toolbar)
    155. [`top`](https://developer.mozilla.org/en-US/docs/Web/API/Window/top)
    156. [`visualViewport`](https://developer.mozilla.org/en-US/docs/Web/API/Window/visualViewport)
    157. [`window`](https://developer.mozilla.org/en-US/docs/Web/API/Window/window)
3.  Methods
    1.  [`alert()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/alert)
    2.  [`atob()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/atob)
    3.  [`back()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/back)
    4.  [`blur()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/blur)
    5.  [`btoa()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/btoa)
    6.  [`cancelAnimationFrame()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/cancelAnimationFrame)
    7.  [`cancelIdleCallback()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/cancelIdleCallback)
    8.  [`captureEvents()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/captureEvents)
    9.  [`clearImmediate()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/clearImmediate)
    10. [`clearInterval()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/clearInterval)
    11. [`clearTimeout()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/clearTimeout)
    12. [`close()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/close)
    13. [`confirm()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/confirm)
    14. [`convertPointFromNodeToPage()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/convertPointFromNodeToPage)
    15. [`convertPointFromPageToNode`](https://developer.mozilla.org/en-US/docs/Web/API/Window/convertPointFromPageToNode)
    16. [`createImageBitmap()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/createImageBitmap)
    17. [`dump()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/dump)
    18. [`fetch()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/fetch)
    19. [`find()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/find)
    20. [`focus()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/focus)
    21. [`forward()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/forward)
    22. [`getComputedStyle()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/getComputedStyle)
    23. [`getDefaultComputedStyle()`](https://developer.mozilla.org/en-US/docs/Web/API/window/getDefaultComputedStyle)
    24. [`getSelection()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/getSelection)
    25. [`home()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/home)
    26. [`matchMedia()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/matchMedia)
    27. [`minimize()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/minimize)
    28. [`moveBy()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/moveBy)
    29. [`moveTo()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/moveTo)
    30. [`open()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/open)
    31. [`openDialog()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/openDialog)
    32. [`postMessage()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/postMessage)
    33. [`print()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/print)
    34. [`prompt()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/prompt)
    35. [`queueMicrotask()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/queueMicrotask)
    36. [`releaseEvents()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/releaseEvents)
    37. [`requestAnimationFrame()`](https://developer.mozilla.org/en-US/docs/Web/API/window/requestAnimationFrame)
    38. [`requestFileSystem()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/requestFileSystem)
    39. [`requestIdleCallback()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/requestIdleCallback)
    40. [`resizeBy()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/resizeBy)
    41. [`resizeTo()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/resizeTo)
    42. [`routeEvent()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/routeEvent)
    43. [`scroll()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/scroll)
    44. [`scrollBy()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/scrollBy)
    45. [`scrollByLines()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/scrollByLines)
    46. [`scrollByPages()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/scrollByPages)
    47. [`scrollTo()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/scrollTo)
    48. [`setCursor()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/setCursor)
    49. [`setImmediate()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/setImmediate)
    50. [`setInterval()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setInterval)
    51. [`setTimeout()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setTimeout)
    52. [`showDirectoryPicker()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/showDirectoryPicker)
    53. [`showModalDialog()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/showModalDialog)
    54. [`showOpenFilePicker()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/showOpenFilePicker)
    55. [`showSaveFilePicker()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/showSaveFilePicker)
    56. [`sizeToContent()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/sizeToContent)
    57. [`stop()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/stop)
    58. [`updateCommands()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/updateCommands)
4.  Events
    1.  [`event`](https://developer.mozilla.org/en-US/docs/Web/API/Window/event)
    2.  [`afterprint`](https://developer.mozilla.org/en-US/docs/Web/API/Window/afterprint_event)
    3.  [`animationcancel`](https://developer.mozilla.org/en-US/docs/Web/API/Window/animationcancel_event)
    4.  [`animationend`](https://developer.mozilla.org/en-US/docs/Web/API/Window/animationend_event)
    5.  [`animationiteration`](https://developer.mozilla.org/en-US/docs/Web/API/Window/animationiteration_event)
    6.  [`beforeprint`](https://developer.mozilla.org/en-US/docs/Web/API/Window/beforeprint_event)
    7.  [`beforeunload`](https://developer.mozilla.org/en-US/docs/Web/API/Window/beforeunload_event)
    8.  [`blur`](https://developer.mozilla.org/en-US/docs/Web/API/Window/blur_event)
    9.  [`copy`](https://developer.mozilla.org/en-US/docs/Web/API/Window/copy_event)
    10. [`cut`](https://developer.mozilla.org/en-US/docs/Web/API/Window/cut_event)
    11. [`DOMContentLoaded`](https://developer.mozilla.org/en-US/docs/Web/API/Window/DOMContentLoaded_event)
    12. [`error`](https://developer.mozilla.org/en-US/docs/Web/API/Window/error_event)
    13. [`focus`](https://developer.mozilla.org/en-US/docs/Web/API/Window/focus_event)
    14. [`hashchange`](https://developer.mozilla.org/en-US/docs/Web/API/Window/hashchange_event)
    15. [`languagechange`](https://developer.mozilla.org/en-US/docs/Web/API/Window/languagechange_event)
    16. *`load`*
    17. [`message`](https://developer.mozilla.org/en-US/docs/Web/API/Window/message_event)
    18. [`messageerror`](https://developer.mozilla.org/en-US/docs/Web/API/Window/messageerror_event)
    19. [`offline`](https://developer.mozilla.org/en-US/docs/Web/API/Window/offline_event)
    20. [`online`](https://developer.mozilla.org/en-US/docs/Web/API/Window/online_event)
    21. [`orientationchange`](https://developer.mozilla.org/en-US/docs/Web/API/Window/orientationchange_event)
    22. [`pagehide`](https://developer.mozilla.org/en-US/docs/Web/API/Window/pagehide_event)
    23. [`pageshow`](https://developer.mozilla.org/en-US/docs/Web/API/Window/pageshow_event)
    24. [`paste`](https://developer.mozilla.org/en-US/docs/Web/API/Window/paste_event)
    25. [`popstate`](https://developer.mozilla.org/en-US/docs/Web/API/Window/popstate_event)
    26. [`rejectionhandled`](https://developer.mozilla.org/en-US/docs/Web/API/Window/rejectionhandled_event)
    27. [`storage`](https://developer.mozilla.org/en-US/docs/Web/API/Window/storage_event)
    28. [`transitioncancel`](https://developer.mozilla.org/en-US/docs/Web/API/Window/transitioncancel_event)
    29. [`unhandledrejection`](https://developer.mozilla.org/en-US/docs/Web/API/Window/unhandledrejection_event)
    30. [`unload`](https://developer.mozilla.org/en-US/docs/Web/API/Window/unload_event)
    31. [`vrdisplayconnect`](https://developer.mozilla.org/en-US/docs/Web/API/Window/vrdisplayconnect_event)
    32. [`vrdisplaydisconnect`](https://developer.mozilla.org/en-US/docs/Web/API/Window/vrdisplaydisconnect_event)
    33. [`vrdisplaypresentchange`](https://developer.mozilla.org/en-US/docs/Web/API/Window/vrdisplaypresentchange_event)

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
