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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers" class="breadcrumb-current-page"><span data-property="name">GlobalEventHandlers</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Properties](#properties_2)
-   [Methods](#methods)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

GlobalEventHandlers
===================

<span class="seoSummary">The **`GlobalEventHandlers`** mixin describes the event handlers common to several interfaces like [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement), [`Document`](https://developer.mozilla.org/en-US/docs/Web/API/Document), or [`Window`](https://developer.mozilla.org/en-US/docs/Web/API/Window).</span> Each of these interfaces can, of course, add more event handlers in addition to the ones listed below.

**Note**: `GlobalEventHandlers` is a mixin and not an interface; you can't actually create an object of type `GlobalEventHandlers`.

[Properties](#properties_2 "Permalink to Properties")
-----------------------------------------------------

*This interface doesn't include any properties except for the event handlers listed below.*

### [Event handlers](#event_handlers "Permalink to Event handlers")

These event handlers are defined on the [`GlobalEventHandlers`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers) mixin, and implemented by [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement), [`Document`](https://developer.mozilla.org/en-US/docs/Web/API/Document), [`Window`](https://developer.mozilla.org/en-US/docs/Web/API/Window), as well as by [`WorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope) for Web Workers.

[`GlobalEventHandlers.onabort`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onabort)  
Is an `event handler` representing the code to be called when the [`abort`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/abort_event "abort") event is raised.

[`GlobalEventHandlers.onanimationcancel`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onanimationcancel)   
An `event handler` called when an `animationcancel` event is sent, indicating that a running [CSS animation](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations) has been canceled.

[`GlobalEventHandlers.onanimationend`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onanimationend)   
An `event handler` called when an `animationend` event is sent, indicating that a [CSS animation](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations) has stopped playing.

[`GlobalEventHandlers.onanimationiteration`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onanimationiteration)   
An `event handler` called when an `animationiteration` event has been sent, indicating that a [CSS animation](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations) has begun playing a new iteration of the animation sequence.

[`GlobalEventHandlers.onanimationstart`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onanimationstart)   
An `event handler` called when an `animationstart` event is sent, indicating that a [CSS animation](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations) has started playing.

[`GlobalEventHandlers.onauxclick`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onauxclick)   
An `event handler` called when an `auxclick` event is sent, indicating that a non-primary button has been pressed on an input device (e.g. a middle mouse button).

[`GlobalEventHandlers.onblur`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onblur)  
Is an `event handler` representing the code to be called when the `blur` event is raised.

[`GlobalEventHandlers.onerror`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onerror)  
Is an <span class="page-not-created">`OnErrorEventHandler`</span> representing the code to be called when the `error` event is raised.

[`GlobalEventHandlers.onfocus`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onfocus)  
Is an `event handler` representing the code to be called when the `focus` event is raised.

[`GlobalEventHandlers.oncancel`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oncancel)  
Is an `event handler` representing the code to be called when the `cancel` event is raised.

[`GlobalEventHandlers.oncanplay`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oncanplay)  
Is an `event handler` representing the code to be called when the `canplay` event is raised.

[`GlobalEventHandlers.oncanplaythrough`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oncanplaythrough)  
Is an `event handler` representing the code to be called when the `canplaythrough` event is raised.

[`GlobalEventHandlers.onchange`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onchange)  
Is an `event handler` representing the code to be called when the `change` event is raised.

[`GlobalEventHandlers.onclick`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onclick)  
Is an `event handler` representing the code to be called when the `click` event is raised.

[`GlobalEventHandlers.onclose`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onclose)  
Is an `event handler` representing the code to be called when the `close` event is raised.

[`GlobalEventHandlers.oncontextmenu`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oncontextmenu)  
Is an `event handler` representing the code to be called when the `contextmenu` event is raised.

[`GlobalEventHandlers.oncuechange`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oncuechange)  
Is an `event handler` representing the code to be called when the `cuechange` event is raised.

[`GlobalEventHandlers.ondblclick`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ondblclick)  
Is an `event handler` representing the code to be called when the `dblclick` event is raised.

[`GlobalEventHandlers.ondrag`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ondrag)  
Is an `event handler` representing the code to be called when the `drag` event is raised.

[`GlobalEventHandlers.ondragend`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ondragend)  
Is an `event handler` representing the code to be called when the `dragend` event is raised.

[`GlobalEventHandlers.ondragenter`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ondragenter)  
Is an `event handler` representing the code to be called when the `dragenter` event is raised.

[`GlobalEventHandlers.ondragexit`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ondragleave)   
Is an `event handler` representing the code to be called when the `dragexit` event is raised.

[`GlobalEventHandlers.ondragleave`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ondragleave)  
Is an `event handler` representing the code to be called when the `dragleave` event is raised.

[`GlobalEventHandlers.ondragover`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ondragover)  
Is an `event handler` representing the code to be called when the `dragover` event is raised.

[`GlobalEventHandlers.ondragstart`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ondragstart)  
Is an `event handler` representing the code to be called when the `dragstart` event is raised.

[`GlobalEventHandlers.ondrop`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ondrop)  
Is an `event handler` representing the code to be called when the `drop` event is raised.

[`GlobalEventHandlers.ondurationchange`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ondurationchange)  
Is an `event handler` representing the code to be called when the `durationchange` event is raised.

[`GlobalEventHandlers.onemptied`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onemptied)  
Is an `event handler` representing the code to be called when the `emptied` event is raised.

[`GlobalEventHandlers.onended`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onended)  
Is an `event handler` representing the code to be called when the `ended` event is raised.

[`GlobalEventHandlers.onformdata`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onformdata)  
Is an `event handler` for processing `formdata` events, fired after the entry list representing the form's data is constructed.

[`GlobalEventHandlers.ongotpointercapture`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ongotpointercapture)  
Is an `event handler` representing the code to be called when the `gotpointercapture` event type is raised.

[`GlobalEventHandlers.oninput`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oninput)  
Is an `event handler` representing the code to be called when the `input` event is raised.

[`GlobalEventHandlers.oninvalid`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oninvalid)  
Is an `event handler` representing the code to be called when the `invalid` event is raised.

[`GlobalEventHandlers.onkeydown`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onkeydown)  
Is an `event handler` representing the code to be called when the `keydown` event is raised.

[`GlobalEventHandlers.onkeypress`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onkeypress)  
Is an `event handler` representing the code to be called when the `keypress` event is raised.

[`GlobalEventHandlers.onkeyup`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onkeyup)  
Is an `event handler` representing the code to be called when the `keyup` event is raised.

[`GlobalEventHandlers.onload`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onload)  
Is an `event handler` representing the code to be called when the `load` event is raised.

[`GlobalEventHandlers.onloadeddata`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onloadeddata)  
Is an `event handler` representing the code to be called when the `loadeddata` event is raised.

[`GlobalEventHandlers.onloadedmetadata`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onloadedmetadata)  
Is an `event handler` representing the code to be called when the `loadedmetadata` event is raised.

[`GlobalEventHandlers.onloadend`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onloadend)  
Is an `event handler` representing the code to be called when the `loadend` event is raised (when progress has stopped on the loading of a resource.)

[`GlobalEventHandlers.onloadstart`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onloadstart)  
Is an `event handler` representing the code to be called when the `loadstart` event is raised (when progress has begun on the loading of a resource.)

[`GlobalEventHandlers.onlostpointercapture`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onlostpointercapture)  
Is an `event handler` representing the code to be called when the `lostpointercapture` event type is raised.

[`GlobalEventHandlers.onmousedown`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmousedown)  
Is an `event handler` representing the code to be called when the `mousedown` event is raised.

[`GlobalEventHandlers.onmouseenter`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmouseenter)  
Is an `event handler` representing the code to be called when the `mouseenter` event is raised.

[`GlobalEventHandlers.onmouseleave`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmouseleave)  
Is an `event handler` representing the code to be called when the `mouseleave` event is raised.

[`GlobalEventHandlers.onmousemove`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmousemove)  
Is an `event handler` representing the code to be called when the `mousemove` event is raised.

[`GlobalEventHandlers.onmouseout`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmouseout)  
Is an `event handler` representing the code to be called when the `mouseout` event is raised.

[`GlobalEventHandlers.onmouseover`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmouseover)  
Is an `event handler` representing the code to be called when the `mouseover` event is raised.

[`GlobalEventHandlers.onmouseup`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmouseup)  
Is an `event handler` representing the code to be called when the `mouseup` event is raised.

[`GlobalEventHandlers.onmousewheel`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmousewheel)   
Is an `event handler` representing the code to be called when the `mousewheel` event is raised. Deprecated. Use `onwheel` instead.

[`GlobalEventHandlers.onwheel`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onwheel)  
Is an `event handler` representing the code to be called when the `wheel` event is raised.

[`GlobalEventHandlers.onpause`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpause)  
Is an `event handler` representing the code to be called when the `pause` event is raised.

[`GlobalEventHandlers.onplay`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onplay)  
Is an `event handler` representing the code to be called when the `play` event is raised.

[`GlobalEventHandlers.onplaying`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onplaying)  
Is an `event handler` representing the code to be called when the `playing` event is raised.

[`GlobalEventHandlers.onpointerdown`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointerdown)  
Is an `event handler` representing the code to be called when the `pointerdown` event is raised.

[`GlobalEventHandlers.onpointermove`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointermove)  
Is an `event handler` representing the code to be called when the `pointermove` event is raised.

[`GlobalEventHandlers.onpointerup`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointerup)  
Is an `event handler` representing the code to be called when the `pointerup` event is raised.

[`GlobalEventHandlers.onpointercancel`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointercancel)  
Is an `event handler` representing the code to be called when the `pointercancel` event is raised.

[`GlobalEventHandlers.onpointerover`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointerover)  
Is an `event handler` representing the code to be called when the `pointerover` event is raised.

[`GlobalEventHandlers.onpointerout`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointerout)  
Is an `event handler` representing the code to be called when the `pointerout` event is raised.

[`GlobalEventHandlers.onpointerenter`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointerenter)  
Is an `event handler` representing the code to be called when the `pointerenter` event is raised.

[`GlobalEventHandlers.onpointerleave`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointerleave)  
Is an `event handler` representing the code to be called when the `pointerleave` event is raised.

<span class="page-not-created">`GlobalEventHandlers.onpointerlockchange`</span>   
Is an `event handler` representing the code to be called when the `pointerlockchange` event is raised.

<span class="page-not-created">`GlobalEventHandlers.onpointerlockerror`</span>   
Is an `event handler` representing the code to be called when the `pointerlockerror` event is raised.

<span class="page-not-created">`GlobalEventHandlers.onprogress`</span>  
Is an `event handler` representing the code to be called when the `progress` event is raised.

<span class="page-not-created">`GlobalEventHandlers.onratechange`</span>  
Is an `event handler` representing the code to be called when the `ratechange` event is raised.

[`GlobalEventHandlers.onreset`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onreset)  
Is an `event handler` representing the code to be called when the `reset` event is raised.

[`GlobalEventHandlers.onresize`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onresize)  
Is an `event handler` representing the code to be called when the `resize` event is raised.

[`GlobalEventHandlers.onscroll`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onscroll)  
Is an `event handler` representing the code to be called when the `scroll` event is raised.

<span class="page-not-created">`GlobalEventHandlers.onseeked`</span>  
Is an `event handler` representing the code to be called when the `seeked` event is raised.

<span class="page-not-created">`GlobalEventHandlers.onseeking`</span>  
Is an `event handler` representing the code to be called when the `seeking` event is raised.

[`GlobalEventHandlers.onselect`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onselect)  
Is an `event handler` representing the code to be called when the `select` event is raised.

[`GlobalEventHandlers.onselectstart`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onselectstart)  
Is an `event handler` representing the code to be called when the `selectionchange` event is raised, i.e. when the user starts to make a new text selection on a web page.

[`GlobalEventHandlers.onselectionchange`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onselectionchange)  
Is an `event handler` representing the code to be called when the `selectionchange` event is raised, i.e. when the text selected on a web page changes.

<span class="page-not-created">`GlobalEventHandlers.onshow`</span>   
Is an `event handler` representing the code to be called when the `show` event is raised.

<span class="page-not-created">`GlobalEventHandlers.onsort`</span>   
Is an `event handler` representing the code to be called when the `sort` event is raised.

<span class="page-not-created">`GlobalEventHandlers.onstalled`</span>  
Is an `event handler` representing the code to be called when the `stalled` event is raised.

[`GlobalEventHandlers.onsubmit`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onsubmit)  
Is an `event handler` representing the code to be called when the `submit` event is raised.

<span class="page-not-created">`GlobalEventHandlers.onsuspend`</span>  
Is an `event handler` representing the code to be called when the `suspend` event is raised.

<span class="page-not-created">`GlobalEventHandlers.ontimeupdate`</span>  
Is an `event handler` representing the code to be called when the `timeupdate` event is raised.

<span class="page-not-created">`GlobalEventHandlers.onvolumechange`</span>  
Is an `event handler` representing the code to be called when the `volumechange` event is raised.

[`GlobalEventHandlers.ontouchcancel`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ontouchcancel)   
Is an `event handler` representing the code to be called when the `touchcancel` event is raised.

[`GlobalEventHandlers.ontouchend`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ontouchend)   
Is an `event handler` representing the code to be called when the `touchend` event is raised.

[`GlobalEventHandlers.ontouchmove`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ontouchmove)   
Is an `event handler` representing the code to be called when the `touchmove` event is raised.

[`GlobalEventHandlers.ontouchstart`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ontouchstart)   
Is an `event handler` representing the code to be called when the `touchstart` event is raised.

[`GlobalEventHandlers.ontransitioncancel`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ontransitioncancel)  
An `event handler` called when a `transitioncancel` event is sent, indicating that a [CSS transition](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions) has been cancelled.

[`GlobalEventHandlers.ontransitionend`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ontransitionend)  
An `event handler` called when a `transitionend` event is sent, indicating that a [CSS transition](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions) has finished playing.

<span class="page-not-created">`GlobalEventHandlers.ontransitionrun`</span>  
An `event handler` called when a `transitionrun` event is sent, indicating that a [CSS transition](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions) is running, though not nessarilty started.

<span class="page-not-created">`GlobalEventHandlers.ontransitionstart`</span>  
An `event handler` called when a `transitionstart` event is sent, indicating that a [CSS transition](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions) has started transitioning.

<span class="page-not-created">`GlobalEventHandlers.onwaiting`</span>  
Is an `event handler` representing the code to be called when the `waiting` event is raised.

[Methods](#methods "Permalink to Methods")
------------------------------------------

*This interface defines no methods.*

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/selection-api/" class="external">Selection API<br />
<span class="small">The definition of 'Extension to GlobalEventHandlers' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds <code>onselectionchange.</code></td></tr><tr class="even"><td><a href="https://w3c.github.io/pointerlock/#extensions-to-the-document-interface" class="external">Pointer Lock<br />
<span class="small">The definition of 'Extension of Document' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Adds <code>onpointerlockchange</code> and <code>onpointerlockerror</code> on <a href="https://developer.mozilla.org/en-US/docs/Web/API/Document"><code>Document</code></a>. It is experimentally implemented on <code>GlobalEventHandlers</code>.</td></tr><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#globaleventhandlers" class="external">HTML Living Standard<br />
<span class="small">The definition of 'GlobalEventHandlers' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change since the latest snapshot, <a href="https://www.w3.org/TR/html51/" class="external" title="The &#39;HTML 5.1&#39; specification">HTML 5.1</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/#globaleventhandlers" class="external">HTML 5.1<br />
<span class="small">The definition of 'GlobalEventHandlers' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Snapshot of <a href="https://html.spec.whatwg.org/multipage/" class="external" title="The &#39;HTML Living Standard&#39; specification">HTML Living Standard</a>. Added <code>onsort</code> since the <a href="https://www.w3.org/TR/html52/" class="external" title="The &#39;HTML5&#39; specification">HTML5</a> snapshot.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/#globaleventhandlers" class="external">HTML5<br />
<span class="small">The definition of 'GlobalEventHandlers' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Snapshot of <a href="https://html.spec.whatwg.org/multipage/" class="external" title="The &#39;HTML Living Standard&#39; specification">HTML Living Standard</a>. Creation of <code>GlobalEventHandlers</code> (properties where on the target before it).</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [`Element`](https://developer.mozilla.org/en-US/docs/Web/API/Element)
-   `event handler`
-   [`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/globaleventhandlers/index.html "Folder: en-us/web/api/globaleventhandlers (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FGlobalEventHandlers%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fglobaleventhandlers%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FGlobalEventHandlers%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fglobaleventhandlers%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F25c169b8c9801610abc0c1c64def24e4bdc9c82b%0A*+Document+last+modified%3A+2021-05-31T01%3A03%3A55.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22GlobalEventHandlers%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/contributors.txt)

Change your languageSelect your preferred language English (US)DeutschEspañolFrançais日本語한국어PolskiPortuguês (do Brasil)Русский中文 (简体)正體中文 (繁體)

Change language

#### Related Topics

1.  **[`GlobalEventHandlers`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers)**
2.  Properties
    1.  [`onabort`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onabort)
    2.  [`onanimationcancel`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onanimationcancel)
    3.  [`onanimationend`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onanimationend)
    4.  [`onanimationiteration`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onanimationiteration)
    5.  [`onauxclick`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onauxclick)
    6.  [`onblur`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onblur)
    7.  [`oncancel`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oncancel)
    8.  [`oncanplay`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oncanplay)
    9.  [`oncanplaythrough`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oncanplaythrough)
    10. [`onchange`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onchange)
    11. [`onclick`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onclick)
    12. [`onclose`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onclose)
    13. [`oncontextmenu`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oncontextmenu)
    14. [`oncuechange`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oncuechange)
    15. [`ondblclick`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ondblclick)
    16. [`ondurationchange`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ondurationchange)
    17. [`onended`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onended)
    18. [`onerror`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onerror)
    19. [`onfocus`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onfocus)
    20. [`onformdata`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onformdata)
    21. [`ongotpointercapture`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ongotpointercapture)
    22. [`oninput`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oninput)
    23. [`oninvalid`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oninvalid)
    24. [`onkeydown`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onkeydown)
    25. [`onkeypress`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onkeypress)
    26. [`onkeyup`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onkeyup)
    27. [`onload`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onload)
    28. [`onloadeddata`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onloadeddata)
    29. [`onloadedmetadata`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onloadedmetadata)
    30. [`onloadend`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onloadend)
    31. [`onloadstart`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onloadstart)
    32. [`onlostpointercapture`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onlostpointercapture)
    33. [`onmousedown`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmousedown)
    34. [`onmouseenter`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmouseenter)
    35. [`onmouseleave`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmouseleave)
    36. [`onmousemove`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmousemove)
    37. [`onmouseout`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmouseout)
    38. [`onmouseover`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmouseover)
    39. [`onmouseup`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmouseup)
    40. [`onpause`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpause)
    41. [`onplay`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onplay)
    42. [`onplaying`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onplaying)
    43. [`onpointercancel`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointercancel)
    44. [`onpointerdown`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointerdown)
    45. [`onpointerenter`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointerenter)
    46. [`onpointerleave`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointerleave)
    47. [`onpointermove`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointermove)
    48. [`onpointerout`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointerout)
    49. [`onpointerover`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointerover)
    50. [`onpointerup`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointerup)
    51. [`onreset`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onreset)
    52. [`onresize`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onresize)
    53. [`onscroll`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onscroll)
    54. [`onselect`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onselect)
    55. [`onselectionchange`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onselectionchange)
    56. [`onselectstart`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onselectstart)
    57. [`onsubmit`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onsubmit)
    58. [`ontouchcancel`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ontouchcancel)
    59. [`ontouchstart`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ontouchstart)
    60. [`ontransitioncancel`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ontransitioncancel)
    61. [`ontransitionend`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ontransitionend)
    62. [`onwheel`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onwheel)
3.  Implemented by:
    1.  [`Document`](https://developer.mozilla.org/en-US/docs/Web/API/Document)
    2.  [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
    3.  [`SVGElement`](https://developer.mozilla.org/en-US/docs/Web/API/SVGElement)
    4.  [`Window`](https://developer.mozilla.org/en-US/docs/Web/API/Window)
    5.  [`XULElement`](https://developer.mozilla.org/en-US/docs/Web/API/XULElement)
4.  Related pages for HTML DOM
    1.  [`BeforeUnloadEvent`](https://developer.mozilla.org/en-US/docs/Web/API/BeforeUnloadEvent)
    2.  [`DOMStringMap`](https://developer.mozilla.org/en-US/docs/Web/API/DOMStringMap)
    3.  [`ErrorEvent`](https://developer.mozilla.org/en-US/docs/Web/API/ErrorEvent)
    4.  [`HTMLAnchorElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAnchorElement)
    5.  [`HTMLAreaElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement)
    6.  [`HTMLAudioElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAudioElement)
    7.  [`HTMLBRElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLBRElement)
    8.  [`HTMLBaseElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLBaseElement)
    9.  [`HTMLBaseFontElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLBaseFontElement)
    10. [`HTMLBodyElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLBodyElement)
    11. [`HTMLButtonElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLButtonElement)
    12. [`HTMLCanvasElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement)
    13. [`HTMLContentElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLContentElement)
    14. [`HTMLDListElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDListElement)
    15. [`HTMLDataElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDataElement)
    16. [`HTMLDataListElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDataListElement)
    17. [`HTMLDialogElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDialogElement)
    18. [`HTMLDivElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDivElement)
    19. [`HTMLDocument`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDocument)
    20. [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
    21. [`HTMLEmbedElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLEmbedElement)
    22. [`HTMLFieldSetElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFieldSetElement)
    23. [`HTMLFormControlsCollection`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormControlsCollection)
    24. [`HTMLFormElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement)
    25. [`HTMLFrameSetElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFrameSetElement)
    26. [`HTMLHRElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLHRElement)
    27. [`HTMLHeadElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLHeadElement)
    28. [`HTMLHeadingElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLHeadingElement)
    29. [`HTMLHtmlElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLHtmlElement)
    30. [`HTMLIFrameElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLIFrameElement)
    31. [`HTMLImageElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement)
    32. [`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement)
    33. [`HTMLIsIndexElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLIsIndexElement)
    34. [`HTMLKeygenElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLKeygenElement)
    35. [`HTMLLIElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLLIElement)
    36. [`HTMLLabelElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLLabelElement)
    37. [`HTMLLegendElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLLegendElement)
    38. [`HTMLLinkElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLLinkElement)
    39. [`HTMLMapElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMapElement)
    40. [`HTMLMediaElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement)
    41. [`HTMLMetaElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMetaElement)
    42. [`HTMLMeterElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMeterElement)
    43. [`HTMLModElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLModElement)
    44. [`HTMLOListElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOListElement)
    45. [`HTMLObjectElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLObjectElement)
    46. [`HTMLOptGroupElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOptGroupElement)
    47. [`HTMLOptionElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOptionElement)
    48. [`HTMLOptionsCollection`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOptionsCollection)
    49. [`HTMLOutputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOutputElement)
    50. [`HTMLParagraphElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLParagraphElement)
    51. [`HTMLParamElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLParamElement)
    52. [`HTMLPictureElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLPictureElement)
    53. [`HTMLPreElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLPreElement)
    54. [`HTMLProgressElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLProgressElement)
    55. [`HTMLQuoteElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLQuoteElement)
    56. [`HTMLScriptElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLScriptElement)
    57. [`HTMLSelectElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement)
    58. [`HTMLShadowElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLShadowElement)
    59. [`HTMLSourceElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSourceElement)
    60. [`HTMLSpanElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSpanElement)
    61. [`HTMLStyleElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLStyleElement)
    62. [`HTMLTableCaptionElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableCaptionElement)
    63. [`HTMLTableCellElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableCellElement)
    64. [`HTMLTableColElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableColElement)
    65. [`HTMLTableDataCellElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableDataCellElement)
    66. [`HTMLTableElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableElement)
    67. [`HTMLTableHeaderCellElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableHeaderCellElement)
    68. [`HTMLTableRowElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableRowElement)
    69. [`HTMLTableSectionElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableSectionElement)
    70. [`HTMLTemplateElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTemplateElement)
    71. [`HTMLTextAreaElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTextAreaElement)
    72. [`HTMLTimeElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTimeElement)
    73. [`HTMLTitleElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTitleElement)
    74. [`HTMLTrackElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTrackElement)
    75. [`HTMLUListElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLUListElement)
    76. [`HTMLUnknownElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLUnknownElement)
    77. [`HTMLVideoElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLVideoElement)
    78. [`HashChangeEvent`](https://developer.mozilla.org/en-US/docs/Web/API/HashChangeEvent)
    79. [`History`](https://developer.mozilla.org/en-US/docs/Web/API/History)
    80. [`ImageData`](https://developer.mozilla.org/en-US/docs/Web/API/ImageData)
    81. [`Location`](https://developer.mozilla.org/en-US/docs/Web/API/Location)
    82. [`MessageChannel`](https://developer.mozilla.org/en-US/docs/Web/API/MessageChannel)
    83. [`MessageEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MessageEvent)
    84. [`MessagePort`](https://developer.mozilla.org/en-US/docs/Web/API/MessagePort)
    85. [`Navigator`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator)
    86. [`NavigatorGeolocation`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorGeolocation)
    87. [`NavigatorID`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorID)
    88. [`NavigatorLanguage`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorLanguage)
    89. [`NavigatorOnLine`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorOnLine)
    90. [`NavigatorPlugins`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorPlugins)
    91. [`PageTransitionEvent`](https://developer.mozilla.org/en-US/docs/Web/API/PageTransitionEvent)
    92. [`Plugin`](https://developer.mozilla.org/en-US/docs/Web/API/Plugin)
    93. [`PluginArray`](https://developer.mozilla.org/en-US/docs/Web/API/PluginArray)
    94. [`PopStateEvent`](https://developer.mozilla.org/en-US/docs/Web/API/PopStateEvent)
    95. [`PortCollection`](https://developer.mozilla.org/en-US/docs/Web/API/PortCollection)
    96. [`PromiseRejectionEvent`](https://developer.mozilla.org/en-US/docs/Web/API/PromiseRejectionEvent)
    97. [`RadioNodeList`](https://developer.mozilla.org/en-US/docs/Web/API/RadioNodeList)
    98. [`Transferable`](https://developer.mozilla.org/en-US/docs/Web/API/Transferable)
    99. [`ValidityState`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState)
    100. [`Window`](https://developer.mozilla.org/en-US/docs/Web/API/Window)
    101. [`WindowBase64`](https://developer.mozilla.org/en-US/docs/Web/API/WindowBase64)
    102. [`WindowEventHandlers`](https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers)
    103. [`WindowTimers`](https://developer.mozilla.org/en-US/docs/Web/API/WindowTimers)

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
