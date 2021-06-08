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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/Document" class="breadcrumb-current-page"><span data-property="name">Document</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Constructor](#constructor)
-   [Properties](#properties)
-   [Methods](#methods)
-   [Events](#events)
-   Non-standard extensions 
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)

Document
========

<span class="seoSummary">The **`Document`** interface represents any web page loaded in the browser and serves as an entry point into the web page's content, which is the [DOM tree](https://developer.mozilla.org/en-US/docs/Web/API/Document_object_model/Using_the_W3C_DOM_Level_1_Core).</span> The DOM tree includes elements such as [`<body>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/body) and [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table), among [many others](https://developer.mozilla.org/en-US/docs/Web/HTML/Element). It provides functionality globally to the document, like how to obtain the page's URL and create new elements in the document.

The `Document` interface describes the common properties and methods for any kind of document. Depending on the document's type (e.g. [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML), [XML](https://developer.mozilla.org/en-US/docs/Web/XML), SVG, …), a larger API is available: HTML documents, served with the `"text/html"` content type, also implement the [`HTMLDocument`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDocument) interface, whereas XML and SVG documents implement the [`XMLDocument`](https://developer.mozilla.org/en-US/docs/Web/API/XMLDocument) interface.

[Constructor](#constructor "Permalink to Constructor")
------------------------------------------------------

[`Document()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/Document "Document()")  
Creates a new `Document` object.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

*This interface also inherits from the [`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node) and [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget) interfaces.*

[`Document.activeElement`](https://developer.mozilla.org/en-US/docs/Web/API/Document/activeElement) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the [`Element`](https://developer.mozilla.org/en-US/docs/Web/API/Element) that currently has focus.

[`Document.body`](https://developer.mozilla.org/en-US/docs/Web/API/Document/body)  
Returns the [`<body>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/body) or [`<frameset>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/frameset) node of the current document.

[`Document.characterSet`](https://developer.mozilla.org/en-US/docs/Web/API/Document/characterSet)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the character set being used by the document.

[`Document.childElementCount`](https://developer.mozilla.org/en-US/docs/Web/API/Document/childElementCount) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the number of child elements of the current document.

[`Document.children`](https://developer.mozilla.org/en-US/docs/Web/API/Document/children) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the child elements of the current document.

[`Document.compatMode`](https://developer.mozilla.org/en-US/docs/Web/API/Document/compatMode)  <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Indicates whether the document is rendered in *quirks* or *strict* mode.

[`Document.contentType`](https://developer.mozilla.org/en-US/docs/Web/API/Document/contentType)  <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the Content-Type from the MIME Header of the current document.

[`Document.doctype`](https://developer.mozilla.org/en-US/docs/Web/API/Document/doctype)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the Document Type Definition (DTD) of the current document.

[`Document.documentElement`](https://developer.mozilla.org/en-US/docs/Web/API/Document/documentElement)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the [`Element`](https://developer.mozilla.org/en-US/docs/Web/API/Element) that is a direct child of the document. For HTML documents, this is normally the [`HTMLHtmlElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLHtmlElement) object representing the document's [`<html>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/html) element.

[`Document.documentURI`](https://developer.mozilla.org/en-US/docs/Web/API/Document/documentURI)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the document location as a string.

[`Document.embeds`](https://developer.mozilla.org/en-US/docs/Web/API/Document/embeds)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a list of the embedded [`<embed>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/embed) elements within the current document.

[`Document.firstElementChild`](https://developer.mozilla.org/en-US/docs/Web/API/Document/firstElementChild) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the first child element of the current document.

[`Document.fonts`](https://developer.mozilla.org/en-US/docs/Web/API/Document/fonts)  
Returns the [`FontFaceSet`](https://developer.mozilla.org/en-US/docs/Web/API/FontFaceSet) interface of the current document.

[`Document.forms`](https://developer.mozilla.org/en-US/docs/Web/API/Document/forms)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a list of the [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form) elements within the current document.

[`Document.fullscreenElement`](https://developer.mozilla.org/en-US/docs/Web/API/Document/fullscreenElement) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
The element that's currently in full screen mode for this document.

[`Document.head`](https://developer.mozilla.org/en-US/docs/Web/API/Document/head)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the [`<head>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/head) element of the current document.

[`Document.hidden`](https://developer.mozilla.org/en-US/docs/Web/API/Document/hidden)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a Boolean value indicating if the page is considered hidden or not.

[`Document.images`](https://developer.mozilla.org/en-US/docs/Web/API/Document/images)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a list of the images in the current document.

[`Document.implementation`](https://developer.mozilla.org/en-US/docs/Web/API/Document/implementation)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the DOM implementation associated with the current document.

[`Document.lastElementChild`](https://developer.mozilla.org/en-US/docs/Web/API/Document/lastElementChild) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the last child element of the current document.

[`Document.links`](https://developer.mozilla.org/en-US/docs/Web/API/Document/links)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a list of all the hyperlinks in the document.

[`Document.mozSyntheticDocument`](https://developer.mozilla.org/en-US/docs/Web/API/Document/mozSyntheticDocument)    
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that is `true` only if this document is synthetic, such as a standalone image, video, audio file, or the like.

[`Document.pictureInPictureElement`](https://developer.mozilla.org/en-US/docs/Web/API/Document/pictureInPictureElement) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the [`Element`](https://developer.mozilla.org/en-US/docs/Web/API/Element) currently being presented in picture-in-picture mode in this document.

[`Document.pictureInPictureEnabled`](https://developer.mozilla.org/en-US/docs/Web/API/Document/pictureInPictureEnabled) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns true if the picture-in-picture feature is enabled.

[`Document.plugins`](https://developer.mozilla.org/en-US/docs/Web/API/Document/plugins)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a list of the available plugins.

[`Document.pointerLockElement`](https://developer.mozilla.org/en-US/docs/Web/API/Document/pointerLockElement) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the element set as the target for mouse events while the pointer is locked. `null` if lock is pending, pointer is unlocked, or if the target is in another document.

[`Document.featurePolicy`](https://developer.mozilla.org/en-US/docs/Web/API/Document/featurePolicy)  <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the [`FeaturePolicy`](https://developer.mozilla.org/en-US/docs/Web/API/FeaturePolicy) interface which provides a simple API for introspecting the feature policies applied to a specific document.

[`Document.scripts`](https://developer.mozilla.org/en-US/docs/Web/API/Document/scripts)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns all the [`<script>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script) elements on the document.

[`Document.scrollingElement`](https://developer.mozilla.org/en-US/docs/Web/API/Document/scrollingElement)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a reference to the [`Element`](https://developer.mozilla.org/en-US/docs/Web/API/Element) that scrolls the document.

[`Document.styleSheets`](https://developer.mozilla.org/en-US/docs/Web/API/Document/styleSheets) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`StyleSheetList`](https://developer.mozilla.org/en-US/docs/Web/API/StyleSheetList) of [`CSSStyleSheet`](https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleSheet) objects for stylesheets explicitly linked into, or embedded in a document.

[`Document.timeline`](https://developer.mozilla.org/en-US/docs/Web/API/Document/timeline)  <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns timeline as a special instance of [`DocumentTimeline`](https://developer.mozilla.org/en-US/docs/Web/API/DocumentTimeline) that is automatically created on page load.

[`Document.visibilityState`](https://developer.mozilla.org/en-US/docs/Web/API/Document/visibilityState)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a `string` denoting the visibility state of the document. Possible values are `visible`, `hidden`, `prerender`, and `unloaded`.

### [Extensions for HTMLDocument](#extensions_for_htmldocument "Permalink to Extensions for HTMLDocument")

*The `Document` interface for HTML documents inherits from the [`HTMLDocument`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDocument) interface or, since HTML5, is extended for such documents.*

[`Document.cookie`](https://developer.mozilla.org/en-US/docs/Web/API/Document/cookie)  
Returns a semicolon-separated list of the cookies for that document or sets a single cookie.

[`Document.defaultView`](https://developer.mozilla.org/en-US/docs/Web/API/Document/defaultView)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a reference to the window object.

[`Document.designMode`](https://developer.mozilla.org/en-US/docs/Web/API/Document/designMode)  
Gets/sets the ability to edit the whole document.

[`Document.dir`](https://developer.mozilla.org/en-US/docs/Web/API/Document/dir)  
Gets/sets directionality (rtl/ltr) of the document.

[`Document.domain`](https://developer.mozilla.org/en-US/docs/Web/API/Document/domain)    
Gets/sets the domain of the current document.

[`Document.lastModified`](https://developer.mozilla.org/en-US/docs/Web/API/Document/lastModified)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the date on which the document was last modified.

[`Document.location`](https://developer.mozilla.org/en-US/docs/Web/API/Document/location)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the URI of the current document.

[`Document.readyState`](https://developer.mozilla.org/en-US/docs/Web/API/Document/readyState)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns loading status of the document.

[`Document.referrer`](https://developer.mozilla.org/en-US/docs/Web/API/Document/referrer)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the URI of the page that linked to this page.

[`Document.title`](https://developer.mozilla.org/en-US/docs/Web/API/Document/title)  
Sets or gets the title of the current document.

[`Document.URL`](https://developer.mozilla.org/en-US/docs/Web/API/Document/URL)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the document location as a string.

### [Event handlers](#event_handlers "Permalink to Event handlers")

[`Document.onafterscriptexecute`](https://developer.mozilla.org/en-US/docs/Web/API/Document/onafterscriptexecute)    
Represents the event handling code for the `afterscriptexecute` event.

[`Document.onbeforescriptexecute`](https://developer.mozilla.org/en-US/docs/Web/API/Document/onbeforescriptexecute)    
Represents the event handling code for the `beforescriptexecute` event.

<span class="page-not-created">`Document.oncopy`</span>    
Represents the event handling code for the `copy` event.

<span class="page-not-created">`Document.oncut`</span>    
Represents the event handling code for the `cut` event.

[`Document.onfullscreenchange`](https://developer.mozilla.org/en-US/docs/Web/API/Document/onfullscreenchange)  
Is an `event handler` representing the code to be called when the `fullscreenchange` event is raised.

[`Document.onfullscreenerror`](https://developer.mozilla.org/en-US/docs/Web/API/Document/onfullscreenerror)  
Is an `event handler` representing the code to be called when the `fullscreenerror` event is raised.

<span class="page-not-created">`Document.onpaste`</span>    
Represents the event handling code for the `paste` event.

<span class="page-not-created">`Document.onreadystatechange`</span>  
Represents the event handling code for the `readystatechange` event.

[`GlobalEventHandlers.onselectionchange`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onselectionchange)    
Is an `event handler` representing the code to be called when the `selectionchange` event is raised.

[`Document.onvisibilitychange`](https://developer.mozilla.org/en-US/docs/Web/API/Document/onvisibilitychange)  
Is an `event handler` representing the code to be called when the `visibilitychange` event is raised.

The `Document` interface is extended with the [`GlobalEventHandlers`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers) interface:

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

### [Deprecated properties](#deprecated_properties "Permalink to Deprecated properties")

[`Document.alinkColor`](https://developer.mozilla.org/en-US/docs/Web/API/Document/alinkColor)    
Returns or sets the color of active links in the document body.

[`Document.all`](https://developer.mozilla.org/en-US/docs/Web/API/Document/all)      
Provides access to all elements in the document — it returns an <span class="page-not-created">`HTMLAllCollection`</span> rooted at the document node. This is a legacy, non-standard property and should not be used.

[`Document.anchors`](https://developer.mozilla.org/en-US/docs/Web/API/Document/anchors)  <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a list of all of the anchors in the document.

[`Document.applets`](https://developer.mozilla.org/en-US/docs/Web/API/Document/applets)  <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns an ordered list of the applets within a document.

[`Document.bgColor`](https://developer.mozilla.org/en-US/docs/Web/API/Document/bgColor)    
Gets/sets the background color of the current document.

[`Document.charset`](https://developer.mozilla.org/en-US/docs/Web/API/Document/characterSet)  <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Alias of [`Document.characterSet`](https://developer.mozilla.org/en-US/docs/Web/API/Document/characterSet). Use this property instead.

[`Document.domConfig`](https://developer.mozilla.org/en-US/docs/Web/API/Document)    
Should return a <span class="page-not-created">`DOMConfiguration`</span> object.

[`Document.fgColor`](https://developer.mozilla.org/en-US/docs/Web/API/Document/fgColor)    
Gets/sets the foreground color, or text color, of the current document.

[`Document.fullscreen`](https://developer.mozilla.org/en-US/docs/Web/API/Document/fullscreen)    
`true` when the document is in <span class="page-not-created">`full-screen mode`</span>.

[`Document.height`](https://developer.mozilla.org/en-US/docs/Web/API/Document/height)      
Gets/sets the height of the current document.

[`Document.inputEncoding`](https://developer.mozilla.org/en-US/docs/Web/API/Document/characterSet)  <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Alias of [`Document.characterSet`](https://developer.mozilla.org/en-US/docs/Web/API/Document/characterSet). Use this property instead.

[`Document.lastStyleSheetSet`](https://developer.mozilla.org/en-US/docs/Web/API/Document/lastStyleSheetSet)  <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the name of the style sheet set that was last enabled. Has the value `null` until the style sheet is changed by setting the value of [`selectedStyleSheetSet`](https://developer.mozilla.org/en-US/docs/Web/API/Document/selectedStyleSheetSet "selectedStyleSheetSet").

[`Document.linkColor`](https://developer.mozilla.org/en-US/docs/Web/API/Document/linkColor)    
Gets/sets the color of hyperlinks in the document.

[`Document.preferredStyleSheetSet`](https://developer.mozilla.org/en-US/docs/Web/API/Document/preferredStyleSheetSet)  <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the preferred style sheet set as specified by the page author.

[`Document.rootElement`](https://developer.mozilla.org/en-US/docs/Web/API/Document/rootElement)    
Like [`Document.documentElement`](https://developer.mozilla.org/en-US/docs/Web/API/Document/documentElement), but only for [`<svg>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/svg) root elements. Use this property instead.

[`Document.selectedStyleSheetSet`](https://developer.mozilla.org/en-US/docs/Web/API/Document/selectedStyleSheetSet)    
Returns which style sheet set is currently in use.

[`Document.styleSheetSets`](https://developer.mozilla.org/en-US/docs/Web/API/Document/styleSheetSets)  <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a list of the style sheet sets available on the document.

[`Document.vlinkColor`](https://developer.mozilla.org/en-US/docs/Web/API/Document/vlinkColor)    
Gets/sets the color of visited hyperlinks.

[`Document.width`](https://developer.mozilla.org/en-US/docs/Web/API/Document/width)      
Returns the width of the current document.

[`Document.xmlEncoding`](https://developer.mozilla.org/en-US/docs/Web/API/Document/xmlEncoding)    
Returns the encoding as determined by the XML declaration.

<span class="page-not-created">`Document.xmlStandalone`</span>    
Returns `true` if the XML declaration specifies the document to be standalone (*e.g.,* An external part of the DTD affects the document's content), else `false`.

[`Document.xmlVersion`](https://developer.mozilla.org/en-US/docs/Web/API/Document/xmlVersion)    
Returns the version number as specified in the XML declaration or `"1.0"` if the declaration is absent.

[Methods](#methods "Permalink to Methods")
------------------------------------------

*This interface also inherits from the [`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node) and [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget) interfaces.*

[`Document.adoptNode()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/adoptNode)  
Adopt node from an external document.

[`Document.append()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/append)  
Inserts a set of [`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node) objects or [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) objects after the last child of the document.

<span class="page-not-created">`Document.captureEvents()`</span>    
See [`Window.captureEvents`](https://developer.mozilla.org/en-US/docs/Web/API/Window/captureEvents).

[`Document.caretPositionFromPoint()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/caretPositionFromPoint)  
Returns a [`CaretPosition`](https://developer.mozilla.org/en-US/docs/Web/API/CaretPosition) object containing the DOM node containing the caret, and caret's character offset within that node.

[`Document.caretRangeFromPoint()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/caretRangeFromPoint)    
Gets a [`Range`](https://developer.mozilla.org/en-US/docs/Web/API/Range) object for the document fragment under the specified coordinates.

[`Document.createAttribute()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createAttribute)  
Creates a new [`Attr`](https://developer.mozilla.org/en-US/docs/Web/API/Attr) object and returns it.

<span class="page-not-created">`Document.createAttributeNS()`</span>  
Creates a new attribute node in a given namespace and returns it.

[`Document.createCDATASection()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createCDATASection)  
Creates a new CDATA node and returns it.

[`Document.createComment()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createComment)  
Creates a new comment node and returns it.

[`Document.createDocumentFragment()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createDocumentFragment)  
Creates a new document fragment.

[`Document.createElement()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createElement)  
Creates a new element with the given tag name.

[`Document.createElementNS()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createElementNS)  
Creates a new element with the given tag name and namespace URI.

[`Document.createEntityReference()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createEntityReference)    
Creates a new entity reference object and returns it.

[`Document.createEvent()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createEvent)  
Creates an event object.

[`Document.createNodeIterator()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createNodeIterator)  
Creates a [`NodeIterator`](https://developer.mozilla.org/en-US/docs/Web/API/NodeIterator) object.

[`Document.createProcessingInstruction()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createProcessingInstruction)  
Creates a new [`ProcessingInstruction`](https://developer.mozilla.org/en-US/docs/Web/API/ProcessingInstruction) object.

[`Document.createRange()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createRange)  
Creates a [`Range`](https://developer.mozilla.org/en-US/docs/Web/API/Range) object.

[`Document.createTextNode()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createTextNode)  
Creates a text node.

[`Document.createTouch()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createTouch)    
Creates a [`Touch`](https://developer.mozilla.org/en-US/docs/Web/API/Touch) object.

[`Document.createTouchList()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createTouchList)    
Creates a [`TouchList`](https://developer.mozilla.org/en-US/docs/Web/API/TouchList) object.

[`Document.createTreeWalker()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createTreeWalker)  
Creates a [`TreeWalker`](https://developer.mozilla.org/en-US/docs/Web/API/TreeWalker) object.

[`Document.elementFromPoint()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/elementFromPoint)  
Returns the topmost element at the specified coordinates.

[`Document.elementsFromPoint()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/elementsFromPoint)  
Returns an array of all elements at the specified coordinates.

[`Document.enableStyleSheetsForSet()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/enableStyleSheetsForSet)    
Enables the style sheets for the specified style sheet set.

[`Document.exitPictureInPicture()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/exitPictureInPicture)  
Remove the video from the floating picture-in-picture window back to its original container.

[`Document.exitPointerLock()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/exitPointerLock)    
Release the pointer lock.

[`Document.getAnimations()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/getAnimations)  
Returns an array of all [`Animation`](https://developer.mozilla.org/en-US/docs/Web/API/Animation) objects currently in effect, whose target elements are descendants of the `document`.

<span class="page-not-created">`Document.getBoxQuads()`</span>   
Returns a list of [`DOMQuad`](https://developer.mozilla.org/en-US/docs/Web/API/DOMQuad) objects representing the CSS fragments of the node.

[`Document.getElementById`](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementById)  
Returns an object reference to the identified element.

[`Document.getElementsByClassName()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementsByClassName)  
Returns a list of elements with the given class name.

[`Document.getElementsByTagName()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementsByTagName)  
Returns a list of elements with the given tag name.

[`Document.getElementsByTagNameNS()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementsByTagNameNS)  
Returns a list of elements with the given tag name and namespace.

[`Document.getSelection()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/getSelection)  
Returns a [`Selection`](https://developer.mozilla.org/en-US/docs/Web/API/Selection) object representing the range of text selected by the user, or the current position of the caret.

[`Document.hasStorageAccess()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/hasStorageAccess)    
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a boolean value indicating whether the document has access to its first-party storage.

[`Document.importNode()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/importNode)  
Returns a clone of a node from an external document.

<span class="page-not-created">`Document.normalizeDocument()`</span>    
Replaces entities, normalizes text nodes, etc.

[`Document.prepend()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/prepend)  
Inserts a set of [`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node) objects or [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) objects before the first child of the document.

[`Document.querySelector()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector)  
Returns the first Element node within the document, in document order, that matches the specified selectors.

[`Document.querySelectorAll()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelectorAll)  
Returns a list of all the Element nodes within the document that match the specified selectors.

[`Document.releaseCapture()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/releaseCapture)    
Releases the current mouse capture if it's on an element in this document.

<span class="page-not-created">`Document.releaseEvents()`</span>      
See [`Window.releaseEvents()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/releaseEvents).

[`Document.replaceChildren()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/replaceChildren)  
Replaces the existing children of a document with a specified new set of children.

[`Document.requestStorageAccess()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/requestStorageAccess)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves if the access to first-party storage was granted, and rejects if access was denied.

<span class="page-not-created">`Document.routeEvent()`</span>      
See [`Window.routeEvent()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/routeEvent).

[`Document.mozSetImageElement()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/mozSetImageElement)    
Allows you to change the element being used as the background image for a specified element ID.

The `Document` interface is extended with the [`XPathEvaluator`](https://developer.mozilla.org/en-US/docs/Web/API/XPathEvaluator) interface:

[`Document.createExpression()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createExpression)  
Compiles an `XPathExpression` which can then be used for (repeated) evaluations.

[`Document.createNSResolver()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createNSResolver)  
Creates an [`XPathNSResolver`](https://developer.mozilla.org/en-US/docs/Web/API/XPathNSResolver) object.

[`Document.evaluate()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/evaluate)  
Evaluates an XPath expression.

### [Extension for HTML documents](#extension_for_html_documents "Permalink to Extension for HTML documents")

The `Document` interface for HTML documents inherit from the [`HTMLDocument`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDocument) interface or, since HTML5, is extended for such documents:

[`Document.clear()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/clear)      
In majority of modern browsers, including recent versions of Firefox and Internet Explorer, this method does nothing.

[`Document.close()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/close)  
Closes a document stream for writing.

[`Document.execCommand()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/execCommand)    
On an editable document, executes a formatting command.

[`Document.getElementsByName()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementsByName)  
Returns a list of elements with the given name.

[`Document.hasFocus()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/hasFocus)  
Returns `true` if the focus is currently located anywhere inside the specified document.

[`Document.open()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/open)  
Opens a document stream for writing.

[`Document.queryCommandEnabled()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/queryCommandEnabled)    
Returns true if the formatting command can be executed on the current range.

<span class="page-not-created">`Document.queryCommandIndeterm()`</span>    
Returns true if the formatting command is in an indeterminate state on the current range.

[`Document.queryCommandState()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/queryCommandState)    
Returns true if the formatting command has been executed on the current range.

[`Document.queryCommandSupported()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/queryCommandSupported)    
Returns true if the formatting command is supported on the current range.

<span class="page-not-created">`Document.queryCommandValue()`</span>    
Returns the current value of the current range for a formatting command.

[`Document.write()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/write)  
Writes text in a document.

[`Document.writeln()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/writeln)  
Writes a line of text in a document.

[Events](#events "Permalink to Events")
---------------------------------------

Listen to these events using `addEventListener()` or by assigning an event listener to the `oneventname` property of this interface.

[`scroll`](https://developer.mozilla.org/en-US/docs/Web/API/Document/scroll_event "scroll")  
Fired when the document view or an element has been scrolled.  
Also available via the [`onscroll`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onscroll "onscroll") property.

[`visibilitychange`](https://developer.mozilla.org/en-US/docs/Web/API/Document/visibilitychange_event "visibilitychange")  
Fired when the content of a tab has become visible or has been hidden.  
Also available via the [`onvisibilitychange`](https://developer.mozilla.org/en-US/docs/Web/API/Document/onvisibilitychange "onvisibilitychange") property.

[`wheel`](https://developer.mozilla.org/en-US/docs/Web/API/Document/wheel_event "wheel")  
Fired when the user rotates a wheel button on a pointing device (typically a mouse).  
Also available via the [`onwheel`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onwheel "onwheel") property.

### [Animation events](#animation_events "Permalink to Animation events")

[`animationcancel`](https://developer.mozilla.org/en-US/docs/Web/API/Document/animationcancel_event "animationcancel")  
Fired when an animation unexpectedly aborts.  
Also available via the [`onanimationcancel`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onanimationcancel "onanimationcancel") property.

[`animationend`](https://developer.mozilla.org/en-US/docs/Web/API/Document/animationend_event "animationend")  
Fired when an animation has completed normally.  
Also available via the [`onanimationend`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onanimationend "onanimationend") property.

[`animationiteration`](https://developer.mozilla.org/en-US/docs/Web/API/Document/animationiteration_event "animationiteration")  
Fired when an animation iteration has completed.  
Also available via the [`onanimationiteration`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onanimationiteration "onanimationiteration") property.

[`animationstart`](https://developer.mozilla.org/en-US/docs/Web/API/Document/animationstart_event "animationstart")  
Fired when an animation starts.  
Also available via the [`onanimationstart`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onanimationstart "onanimationstart") property.

### [Clipboard events](#clipboard_events "Permalink to Clipboard events")

[`copy`](https://developer.mozilla.org/en-US/docs/Web/API/Document/copy_event "copy")  
Fired when the user initiates a copy action through the browser's user interface.  
Also available via the [`oncopy`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/oncopy "oncopy") property.

[`cut`](https://developer.mozilla.org/en-US/docs/Web/API/Document/cut_event "cut")  
Fired when the user initiates a cut action through the browser's user interface.  
Also available via the [`oncut`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/oncut "oncut") property.

[`paste`](https://developer.mozilla.org/en-US/docs/Web/API/Document/paste_event "paste")  
Fired when the user initiates a paste action through the browser's user interface.  
Also available via the [`onpaste`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/onpaste "onpaste") property.

### [Drag & drop events](#drag_drop_events "Permalink to Drag & drop events")

[`drag`](https://developer.mozilla.org/en-US/docs/Web/API/Document/drag_event "drag")  
Fired every few hundred milliseconds as an element or text selection is being dragged by the user.  
Also available via the [`ondrag`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ondrag "ondrag") property.

[`dragend`](https://developer.mozilla.org/en-US/docs/Web/API/Document/dragend_event "dragend")  
Fired when a drag operation is being ended (by releasing a mouse button or hitting the escape key).  
Also available via the [`ondragend`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ondragend "ondragend") property.

[`dragenter`](https://developer.mozilla.org/en-US/docs/Web/API/Document/dragenter_event "dragenter")  
Fired when a dragged element or text selection enters a valid drop target.  
Also available via the [`ondragenter`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ondragenter "ondragenter") property.

[`dragleave`](https://developer.mozilla.org/en-US/docs/Web/API/Document/dragleave_event "dragleave")  
Fired when a dragged element or text selection leaves a valid drop target.  
Also available via the [`ondragleave`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ondragleave "ondragleave") property.

[`dragover`](https://developer.mozilla.org/en-US/docs/Web/API/Document/dragover_event "dragover")  
Fired when an element or text selection is being dragged over a valid drop target (every few hundred milliseconds).  
Also available via the [`ondragover`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ondragover "ondragover") property.

[`dragstart`](https://developer.mozilla.org/en-US/docs/Web/API/Document/dragstart_event "dragstart")  
Fired when the user starts dragging an element or text selection.  
Also available via the [`ondragstart`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ondragstart "ondragstart") property.

[`drop`](https://developer.mozilla.org/en-US/docs/Web/API/Document/drop_event "drop")  
Fired when an element or text selection is dropped on a valid drop target.  
Also available via the [`ondrop`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ondrop "ondrop") property.

### [Fullscreen events](#fullscreen_events "Permalink to Fullscreen events")

[`fullscreenchange`](https://developer.mozilla.org/en-US/docs/Web/API/Document/fullscreenchange_event "fullscreenchange")  
Fired when the `Document` transitions into or out of [full-screen](https://developer.mozilla.org/en-US/docs/Web/API/Fullscreen_API/Guide) mode.  
Also available via the [`onfullscreenchange`](https://developer.mozilla.org/en-US/docs/Web/API/Document/onfullscreenchange "onfullscreenchange") property.

`fullscreenerror`  
Fired if an error occurs while attempting to switch into or out of [full-screen](https://developer.mozilla.org/en-US/docs/Web/API/Fullscreen_API/Guide) mode.  
Also available via the  [`onfullscreenerror`](https://developer.mozilla.org/en-US/docs/Web/API/Document/onfullscreenerror "onfullscreenerror") property.

### [Keyboard events](#keyboard_events "Permalink to Keyboard events")

[`keydown`](https://developer.mozilla.org/en-US/docs/Web/API/Document/keydown_event "keydown")  
Fired when a key is pressed.  
Also available via the [`onkeydown`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onkeydown "onkeydown") property.

[`keypress`](https://developer.mozilla.org/en-US/docs/Web/API/Document/keypress_event "keypress")  
Fired when a key that produces a character value is pressed down. 

  
Also available via the [`onkeypress`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onkeypress "onkeypress") property.

[`keyup`](https://developer.mozilla.org/en-US/docs/Web/API/Document/keyup_event "keyup")  
Fired when a key is released.  
Also available via the [`onkeyup`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onkeyup "onkeyup") property.

### [Load & unload events](#load_unload_events "Permalink to Load & unload events")

[`DOMContentLoaded`](https://developer.mozilla.org/en-US/docs/Web/API/Document/DOMContentLoaded_event "DOMContentLoaded")  
Fired when the document has been completely loaded and parsed, without waiting for stylesheets, images, and subframes to finish loading.

[`readystatechange`](https://developer.mozilla.org/en-US/docs/Web/API/Document/readystatechange_event "readystatechange")  
Fired when the [`readyState`](https://developer.mozilla.org/en-US/docs/Web/API/Document/readyState "readyState") attribute of a document has changed.  
Also available via the `onreadystatechange` property.

### [Pointer events](#pointer_events "Permalink to Pointer events")

[`gotpointercapture`](https://developer.mozilla.org/en-US/docs/Web/API/Document/gotpointercapture_event "gotpointercapture")  
Fired when an element captures a pointer using `setPointerCapture()`.  
Also available via the [`ongotpointercapture`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ongotpointercapture "ongotpointercapture") property.

[`lostpointercapture`](https://developer.mozilla.org/en-US/docs/Web/API/Document/lostpointercapture_event "lostpointercapture")  
Fired when a [captured pointer](https://developer.mozilla.org/en-US/docs/Web/API/Pointer_events#pointer_capture) is released.  
Also available via the [`onlostpointercapture`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onlostpointercapture "onlostpointercapture") property.

[`pointercancel`](https://developer.mozilla.org/en-US/docs/Web/API/Document/pointercancel_event "pointercancel")  
Fired when a pointer event is canceled.  
Also available via the [`onpointercancel`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointercancel "onpointercancel") property.

[`pointerdown`](https://developer.mozilla.org/en-US/docs/Web/API/Document/pointerdown_event "pointerdown")  
Fired when a pointer becomes active.  
Also available via the [`onpointerdown`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointerdown "onpointerdown") property.

[`pointerenter`](https://developer.mozilla.org/en-US/docs/Web/API/Document/pointerenter_event "pointerenter")  
Fired when a pointer is moved into the hit test boundaries of an element or one of its descendants.  
Also available via the [`onpointerenter`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointerenter "onpointerenter") property.

[`pointerleave`](https://developer.mozilla.org/en-US/docs/Web/API/Document/pointerleave_event "pointerleave")  
Fired when a pointer is moved out of the hit test boundaries of an element.  
Also available via the [`onpointerleave`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointerleave "onpointerleave") property.

[`pointerlockchange`](https://developer.mozilla.org/en-US/docs/Web/API/Document/pointerlockchange_event "pointerlockchange")  
Fired when the pointer is locked/unlocked.  
Also available via the <span class="page-not-created">`onpointerlockchange`</span> property.

[`pointerlockerror`](https://developer.mozilla.org/en-US/docs/Web/API/Document/pointerlockerror_event "pointerlockerror")  
Fired when locking the pointer failed.  
Also available via the <span class="page-not-created">`onpointerlockerror`</span> property.

[`pointermove`](https://developer.mozilla.org/en-US/docs/Web/API/Document/pointermove_event "pointermove")  
Fired when a pointer changes coordinates.  
Also available via the [`onpointermove`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointermove "onpointermove") property.

[`pointerout`](https://developer.mozilla.org/en-US/docs/Web/API/Document/pointerout_event "pointerout")  
Fired when a pointer is moved out of the *hit test* boundaries of an element (among other reasons).  
Also available via the [`onpointerout`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointerout "onpointerout") property.

[`pointerover`](https://developer.mozilla.org/en-US/docs/Web/API/Document/pointerover_event "pointerover")  
Fired when a pointer is moved into an element's hit test boundaries.  
Also available via the [`onpointerover`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointerover "onpointerover") property.

[`pointerup`](https://developer.mozilla.org/en-US/docs/Web/API/Document/pointerup_event "pointerup")  
Fired when a pointer is no longer active.  
Also available via the [`onpointerup`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointerup "onpointerup") property.

### [Selection events](#selection_events "Permalink to Selection events")

[`selectionchange`](https://developer.mozilla.org/en-US/docs/Web/API/Document/selectionchange_event "selectionchange")  
Fired when the current text selection on a document is changed.  
Also available via the [`onselectionchange`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onselectionchange "onselectionchange") property.

[`selectstart`](https://developer.mozilla.org/en-US/docs/Web/API/Document/selectstart_event "selectstart")  
Fired when the user begins a new selection.  
Also available via the [`onselectstart`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onselectstart "onselectstart") property.

### [Touch events](#touch_events "Permalink to Touch events")

[`touchcancel`](https://developer.mozilla.org/en-US/docs/Web/API/Document/touchcancel_event "touchcancel")  
Fired when one or more touch points have been disrupted in an implementation-specific manner (for example, too many touch points are created).  
Also available via the [`ontouchcancel`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ontouchcancel "ontouchcancel") property.

[`touchend`](https://developer.mozilla.org/en-US/docs/Web/API/Document/touchend_event "touchend")  
Fired when one or more touch points are removed from the touch surface.  
Also available via the [`ontouchend`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ontouchend "ontouchend") property

[`touchmove`](https://developer.mozilla.org/en-US/docs/Web/API/Document/touchmove_event "touchmove")  
Fired when one or more touch points are moved along the touch surface.  
Also available via the [`ontouchmove`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ontouchmove "ontouchmove") property

[`touchstart`](https://developer.mozilla.org/en-US/docs/Web/API/Document/touchstart_event "touchstart")  
Fired when one or more touch points are placed on the touch surface.  
Also available via the [`ontouchstart`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ontouchstart "ontouchstart") property

### [Transition events](#transition_events "Permalink to Transition events")

[`transitioncancel`](https://developer.mozilla.org/en-US/docs/Web/API/Document/transitioncancel_event "transitioncancel")  
Fired when a [CSS transition](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions) is canceled.  
Also available via the [`ontransitioncancel`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ontransitioncancel "ontransitioncancel") property.

[`transitionend`](https://developer.mozilla.org/en-US/docs/Web/API/Document/transitionend_event "transitionend")  
Fired when a [CSS transition](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions) has completed.  
Also available via the [`ontransitionend`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ontransitionend "ontransitionend") property.

[`transitionrun`](https://developer.mozilla.org/en-US/docs/Web/API/Document/transitionrun_event "transitionrun")  
Fired when a [CSS transition](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions) is first created.  
Also available via the <span class="page-not-created">`ontransitionrun`</span> property.

[`transitionstart`](https://developer.mozilla.org/en-US/docs/Web/API/Document/transitionstart_event "transitionstart")  
Fired when a [CSS transition](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions) has actually started.  
Also available via the <span class="page-not-created">`ontransitionstart`</span> property.

[Non-standard extensions ](#non-standard_extensions_non-standard_inline "Permalink to Non-standard extensions 
    
")
--------------------------------------------------------------------------------------------------------------

#### Non-standard

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

### [Firefox notes](#firefox_notes "Permalink to Firefox notes")

Mozilla defines a set of non-standard properties made only for XUL content:

[`Document.currentScript`](https://developer.mozilla.org/en-US/docs/Web/API/Document/currentScript)    
Returns the [`<script>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script) element that is currently executing.

[`Document.documentURIObject`](https://developer.mozilla.org/en-US/docs/Web/API/Document/documentURIObject)  
(**Mozilla add-ons only!**) Returns the <span class="page-not-created">`nsIURI`</span> object representing the URI of the document. This property only has special meaning in privileged JavaScript code (with UniversalXPConnect privileges).

[`Document.popupNode`](https://developer.mozilla.org/en-US/docs/Web/API/Document/popupNode)  
Returns the node upon which a popup was invoked.

[`Document.tooltipNode`](https://developer.mozilla.org/en-US/docs/Web/API/Document/tooltipNode)  
Returns the node which is the target of the current tooltip.

Mozilla also define some non-standard methods:

<span class="page-not-created">`Document.execCommandShowHelp()`</span>   
This method never did anything and always threw an exception, so it was removed in Gecko 14.0 (Firefox 14.0 / Thunderbird 14.0 / SeaMonkey 2.11).

[`Document.getBoxObjectFor()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/getBoxObjectFor)    
Use the [`Element.getBoundingClientRect()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/getBoundingClientRect) method instead.

<span class="page-not-created">`Document.loadOverlay()`</span>   
Loads a <a href="https://developer.mozilla.org/en-US/docs/XUL_Overlays" class="page-not-created" title="This is a link to an unwritten page">XUL overlay</a> dynamically. This only works in XUL documents.

<span class="page-not-created">`Document.queryCommandText()`</span>   
This method never did anything but throw an exception, and was removed in Gecko 14 (Firefox 14 / Thunderbird 14 / SeaMonkey 2.11).

### [Internet Explorer notes](#internet_explorer_notes "Permalink to Internet Explorer notes")

Microsoft defines some non-standard properties:

<span class="page-not-created">`Document.fileSize`</span>\*      
Returns size in bytes of the document. Starting with Internet Explorer 11, that property is no longer supported. See <a href="https://msdn.microsoft.com/en-us/library/ms533752(v=VS.85).aspx" class="external">MSDN</a>.

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#interface-document" class="external">DOM<br />
<span class="small">The definition of 'Document' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Intend to supersede DOM 3</td></tr><tr class="even"><td><a href="https://html.spec.whatwg.org/multipage/dom.html#the-document-object" class="external">HTML Living Standard<br />
<span class="small">The definition of 'Document' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Turn the <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLDocument"><code>HTMLDocument</code></a> interface into a <code>Document</code> extension.</td></tr><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#extensions-to-the-document-interface" class="external">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'Document' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Extend the <code>Document</code> interface</td></tr><tr class="even"><td><a href="https://w3c.github.io/pointerlock/#extensions-to-the-document-interface" class="external">Pointer Lock<br />
<span class="small">The definition of 'Document' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Extend the <code>Document</code> interface</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/page-visibility/#extensions-to-the-document-interface" class="external">Page Visibility (Second Edition)<br />
<span class="small">The definition of 'Document' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Extend the <code>Document</code> interface with the <code>visibilityState</code> and <code>hidden</code> attributes and the <code>onvisibilitychange</code> event listener.</td></tr><tr class="even"><td><a href="https://w3c.github.io/selection-api/#extensions-to-document-interface" class="external">Selection API<br />
<span class="small">The definition of 'Document' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds <code>getSelection()</code>, <code>onselectstart</code> and <code>onselectionchange</code>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/dom/#interface-document" class="external">DOM4<br />
<span class="small">The definition of 'Document' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Supersede DOM 3</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-3-Core/#i-Document" class="external">Document Object Model (DOM) Level 3 Core Specification<br />
<span class="small">The definition of 'Document' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Supersede DOM 2</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-3-XPath/xpath.html#XPathEvaluator" class="external">Document Object Model (DOM) Level 3 XPath Specification<br />
<span class="small">The definition of 'XPathEvaluator' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Define the <a href="https://developer.mozilla.org/en-US/docs/Web/API/XPathEvaluator"><code>XPathEvaluator</code></a> interface which extend document.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Core/#i-Document" class="external">Document Object Model (DOM) Level 2 Core Specification<br />
<span class="small">The definition of 'Document' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Supersede DOM 1</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/#i-Document" class="external">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'Document' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition for the interface</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/document/index.html "Folder: en-us/web/api/document (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FDocument%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fdocument%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FDocument%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fdocument%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F5394f9462d26e4f9ee38a12259311416d3fa1678%0A*+Document+last+modified%3A+2021-06-02T17%3A47%3A42.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22Document%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Jun 2, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/Document/contributors.txt)

Change your languageSelect your preferred language English (US)DeutschEspañolFrançais日本語한국어PolskiPortuguês (do Brasil)Русский中文 (简体)正體中文 (繁體)

Change language

#### Related Topics

1.  **[Document Object Model](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model)**
2.  **[`Document`](https://developer.mozilla.org/en-US/docs/Web/API/Document)**
3.  Constructor
    1.  [`Document()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/Document)
4.  Properties
    1.  [`activeElement`](https://developer.mozilla.org/en-US/docs/Web/API/Document/activeElement)
    2.  [`alinkColor`](https://developer.mozilla.org/en-US/docs/Web/API/Document/alinkColor)
    3.  [`all`](https://developer.mozilla.org/en-US/docs/Web/API/Document/all)
    4.  [`anchors`](https://developer.mozilla.org/en-US/docs/Web/API/Document/anchors)
    5.  [`applets`](https://developer.mozilla.org/en-US/docs/Web/API/Document/applets)
    6.  [`bgColor`](https://developer.mozilla.org/en-US/docs/Web/API/Document/bgColor)
    7.  [`body`](https://developer.mozilla.org/en-US/docs/Web/API/Document/body)
    8.  [`characterSet`](https://developer.mozilla.org/en-US/docs/Web/API/Document/characterSet)
    9.  [`childElementCount`](https://developer.mozilla.org/en-US/docs/Web/API/Document/childElementCount)
    10. [`children`](https://developer.mozilla.org/en-US/docs/Web/API/Document/children)
    11. [`compatMode`](https://developer.mozilla.org/en-US/docs/Web/API/Document/compatMode)
    12. [`contentType`](https://developer.mozilla.org/en-US/docs/Web/API/Document/contentType)
    13. [`currentScript`](https://developer.mozilla.org/en-US/docs/Web/API/Document/currentScript)
    14. [`defaultView`](https://developer.mozilla.org/en-US/docs/Web/API/Document/defaultView)
    15. [`designMode`](https://developer.mozilla.org/en-US/docs/Web/API/Document/designMode)
    16. [`dir`](https://developer.mozilla.org/en-US/docs/Web/API/Document/dir)
    17. [`doctype`](https://developer.mozilla.org/en-US/docs/Web/API/Document/doctype)
    18. [`documentElement`](https://developer.mozilla.org/en-US/docs/Web/API/Document/documentElement)
    19. [`documentURI`](https://developer.mozilla.org/en-US/docs/Web/API/Document/documentURI)
    20. [`documentURIObject`](https://developer.mozilla.org/en-US/docs/Web/API/Document/documentURIObject)
    21. [`domain`](https://developer.mozilla.org/en-US/docs/Web/API/Document/domain)
    22. [`embeds`](https://developer.mozilla.org/en-US/docs/Web/API/Document/embeds)
    23. [`fgColor`](https://developer.mozilla.org/en-US/docs/Web/API/Document/fgColor)
    24. [`firstElementChild`](https://developer.mozilla.org/en-US/docs/Web/API/Document/firstElementChild)
    25. [`forms`](https://developer.mozilla.org/en-US/docs/Web/API/Document/forms)
    26. [`fullscreen`](https://developer.mozilla.org/en-US/docs/Web/API/Document/fullscreen)
    27. [`fullscreenElement`](https://developer.mozilla.org/en-US/docs/Web/API/Document/fullscreenElement)
    28. [`fullscreenEnabled`](https://developer.mozilla.org/en-US/docs/Web/API/Document/fullscreenEnabled)
    29. [`head`](https://developer.mozilla.org/en-US/docs/Web/API/Document/head)
    30. [`height`](https://developer.mozilla.org/en-US/docs/Web/API/Document/height)
    31. [`hidden`](https://developer.mozilla.org/en-US/docs/Web/API/Document/hidden)
    32. [`images`](https://developer.mozilla.org/en-US/docs/Web/API/Document/images)
    33. [`implementation`](https://developer.mozilla.org/en-US/docs/Web/API/Document/implementation)
    34. [`lastElementChild`](https://developer.mozilla.org/en-US/docs/Web/API/Document/lastElementChild)
    35. [`lastModified`](https://developer.mozilla.org/en-US/docs/Web/API/Document/lastModified)
    36. [`lastStyleSheetSet`](https://developer.mozilla.org/en-US/docs/Web/API/Document/lastStyleSheetSet)
    37. [`linkColor`](https://developer.mozilla.org/en-US/docs/Web/API/Document/linkColor)
    38. [`links`](https://developer.mozilla.org/en-US/docs/Web/API/Document/links)
    39. [`location`](https://developer.mozilla.org/en-US/docs/Web/API/Document/location)
    40. [`mozSyntheticDocument`](https://developer.mozilla.org/en-US/docs/Web/API/Document/mozSyntheticDocument)
    41. [`onabort`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onabort)
    42. [`onafterscriptexecute`](https://developer.mozilla.org/en-US/docs/Web/API/Document/onafterscriptexecute)
    43. [`onanimationcancel`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onanimationcancel)
    44. [`onanimationend`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onanimationend)
    45. [`onanimationiteration`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onanimationiteration)
    46. [`onauxclick`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onauxclick)
    47. [`onbeforescriptexecute`](https://developer.mozilla.org/en-US/docs/Web/API/Document/onbeforescriptexecute)
    48. [`onblur`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onblur)
    49. [`oncancel`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oncancel)
    50. [`oncanplay`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oncanplay)
    51. [`oncanplaythrough`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oncanplaythrough)
    52. [`onchange`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onchange)
    53. [`onclick`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onclick)
    54. [`onclose`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onclose)
    55. [`oncontextmenu`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oncontextmenu)
    56. [`oncuechange`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oncuechange)
    57. [`ondblclick`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ondblclick)
    58. [`ondurationchange`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ondurationchange)
    59. [`onended`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onended)
    60. [`onerror`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onerror)
    61. [`onfocus`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onfocus)
    62. [`onformdata`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onformdata)
    63. [`onfullscreenchange`](https://developer.mozilla.org/en-US/docs/Web/API/Document/onfullscreenchange)
    64. [`onfullscreenerror`](https://developer.mozilla.org/en-US/docs/Web/API/Document/onfullscreenerror)
    65. [`ongotpointercapture`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ongotpointercapture)
    66. [`oninput`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oninput)
    67. [`oninvalid`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oninvalid)
    68. [`onkeydown`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onkeydown)
    69. [`onkeypress`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onkeypress)
    70. [`onkeyup`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onkeyup)
    71. [`onload`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onload)
    72. [`onloadeddata`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onloadeddata)
    73. [`onloadedmetadata`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onloadedmetadata)
    74. [`onloadend`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onloadend)
    75. [`onloadstart`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onloadstart)
    76. [`onlostpointercapture`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onlostpointercapture)
    77. [`onmousedown`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmousedown)
    78. [`onmouseenter`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmouseenter)
    79. [`onmouseleave`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmouseleave)
    80. [`onmousemove`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmousemove)
    81. [`onmouseout`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmouseout)
    82. [`onmouseover`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmouseover)
    83. [`onmouseup`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmouseup)
    84. [`onoffline`](https://developer.mozilla.org/en-US/docs/Web/API/Document/onoffline)
    85. [`ononline`](https://developer.mozilla.org/en-US/docs/Web/API/Document/ononline)
    86. [`onpause`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpause)
    87. [`onplay`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onplay)
    88. [`onplaying`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onplaying)
    89. [`onpointercancel`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointercancel)
    90. [`onpointerdown`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointerdown)
    91. [`onpointerenter`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointerenter)
    92. [`onpointerleave`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointerleave)
    93. [`onpointermove`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointermove)
    94. [`onpointerout`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointerout)
    95. [`onpointerover`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointerover)
    96. [`onpointerup`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointerup)
    97. [`onreset`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onreset)
    98. [`onresize`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onresize)
    99. [`onscroll`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onscroll)
    100. [`onselect`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onselect)
    101. [`onselectionchange`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onselectionchange)
    102. [`onselectstart`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onselectstart)
    103. [`onsubmit`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onsubmit)
    104. [`ontouchcancel`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ontouchcancel)
    105. [`ontouchstart`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ontouchstart)
    106. [`ontransitioncancel`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ontransitioncancel)
    107. [`ontransitionend`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ontransitionend)
    108. [`onvisibilitychange`](https://developer.mozilla.org/en-US/docs/Web/API/Document/onvisibilitychange)
    109. [`onwheel`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onwheel)
    110. [`origin`](https://developer.mozilla.org/en-US/docs/Web/API/Document/origin)
    111. [`pictureInPictureElement`](https://developer.mozilla.org/en-US/docs/Web/API/Document/pictureInPictureElement)
    112. [`pictureInPictureEnabled`](https://developer.mozilla.org/en-US/docs/Web/API/Document/pictureInPictureEnabled)
    113. [`plugins`](https://developer.mozilla.org/en-US/docs/Web/API/Document/plugins)
    114. [`pointerLockElement`](https://developer.mozilla.org/en-US/docs/Web/API/Document/pointerLockElement)
    115. [`popupNode`](https://developer.mozilla.org/en-US/docs/Web/API/Document/popupNode)
    116. [`preferredStyleSheetSet`](https://developer.mozilla.org/en-US/docs/Web/API/Document/preferredStyleSheetSet)
    117. [`readyState`](https://developer.mozilla.org/en-US/docs/Web/API/Document/readyState)
    118. [`referrer`](https://developer.mozilla.org/en-US/docs/Web/API/Document/referrer)
    119. [`rootElement`](https://developer.mozilla.org/en-US/docs/Web/API/Document/rootElement)
    120. [`scripts`](https://developer.mozilla.org/en-US/docs/Web/API/Document/scripts)
    121. [`scrollingElement`](https://developer.mozilla.org/en-US/docs/Web/API/Document/scrollingElement)
    122. [`selectedStyleSheetSet`](https://developer.mozilla.org/en-US/docs/Web/API/Document/selectedStyleSheetSet)
    123. [`styleSheets`](https://developer.mozilla.org/en-US/docs/Web/API/Document/styleSheets)
    124. [`styleSheetSets`](https://developer.mozilla.org/en-US/docs/Web/API/Document/styleSheetSets)
    125. [`timeline`](https://developer.mozilla.org/en-US/docs/Web/API/Document/timeline)
    126. [`title`](https://developer.mozilla.org/en-US/docs/Web/API/Document/title)
    127. [`tooltipNode`](https://developer.mozilla.org/en-US/docs/Web/API/Document/tooltipNode)
    128. [`URL`](https://developer.mozilla.org/en-US/docs/Web/API/Document/URL)
    129. [`visibilityState`](https://developer.mozilla.org/en-US/docs/Web/API/Document/visibilityState)
    130. [`vlinkColor`](https://developer.mozilla.org/en-US/docs/Web/API/Document/vlinkColor)
    131. [`width`](https://developer.mozilla.org/en-US/docs/Web/API/Document/width)
    132. [`xmlEncoding`](https://developer.mozilla.org/en-US/docs/Web/API/Document/xmlEncoding)
    133. [`xmlVersion`](https://developer.mozilla.org/en-US/docs/Web/API/Document/xmlVersion)
5.  Methods
    1.  [`adoptNode()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/adoptNode)
    2.  [`append()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/append)
    3.  [`caretPositionFromPoint()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/caretPositionFromPoint)
    4.  [`caretRangeFromPoint()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/caretRangeFromPoint)
    5.  [`clear()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/clear)
    6.  [`close()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/close)
    7.  [`createAttribute()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createAttribute)
    8.  [`createCDATASection()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createCDATASection)
    9.  [`createComment()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createComment)
    10. [`createDocumentFragment()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createDocumentFragment)
    11. [`createElement()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createElement)
    12. [`createElementNS()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createElementNS)
    13. [`createEntityReference()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createEntityReference)
    14. [`createEvent()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createEvent)
    15. [`createExpression()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createExpression)
    16. [`createExpression()`](https://developer.mozilla.org/en-US/docs/Web/API/XPathEvaluator/createExpression)
    17. [`createNodeIterator()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createNodeIterator)
    18. [`createNSResolver()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createNSResolver)
    19. [`createNSResolver()`](https://developer.mozilla.org/en-US/docs/Web/API/XPathEvaluator/createNSResolver)
    20. [`createProcessingInstruction()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createProcessingInstruction)
    21. [`createRange()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createRange)
    22. [`createTextNode()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createTextNode)
    23. [`createTouch()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createTouch)
    24. [`createTouchList()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createTouchList)
    25. [`createTreeWalker()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createTreeWalker)
    26. [`elementFromPoint()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/elementFromPoint)
    27. [`elementsFromPoint()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/elementsFromPoint)
    28. [`enableStyleSheetsForSet()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/enableStyleSheetsForSet)
    29. [`evaluate()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/evaluate)
    30. [`evaluate()`](https://developer.mozilla.org/en-US/docs/Web/API/XPathEvaluator/evaluate)
    31. [`execCommand()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/execCommand)
    32. [`exitFullscreen()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/exitFullscreen)
    33. [`exitPictureInPicture()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/exitPictureInPicture)
    34. [`exitPointerLock()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/exitPointerLock)
    35. [`getAnimations()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/getAnimations)
    36. [`getBoxObjectFor()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/getBoxObjectFor)
    37. [`getElementById()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementById)
    38. [`getElementsByClassName()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementsByClassName)
    39. [`getElementsByName()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementsByName)
    40. [`getElementsByTagName()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementsByTagName)
    41. [`getElementsByTagNameNS()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementsByTagNameNS)
    42. [`getSelection()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/getSelection)
    43. [`hasFocus()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/hasFocus)
    44. [`hasStorageAccess()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/hasStorageAccess)
    45. [`importNode()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/importNode)
    46. [`mozSetImageElement()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/mozSetImageElement)
    47. [`open()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/open)
    48. [`prepend()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/prepend)
    49. [`queryCommandEnabled()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/queryCommandEnabled)
    50. [`queryCommandSupported()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/queryCommandSupported)
    51. [`querySelector()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector)
    52. [`querySelectorAll()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelectorAll)
    53. [`registerElement()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/registerElement)
    54. [`releaseCapture()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/releaseCapture)
    55. [`replaceChildren()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/replaceChildren)
    56. [`requestStorageAccess()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/requestStorageAccess)
    57. [`write()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/write)
    58. [`writeln()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/writeln)
6.  Events
    1.  [`animationcancel`](https://developer.mozilla.org/en-US/docs/Web/API/Document/animationcancel_event)
    2.  [`animationend`](https://developer.mozilla.org/en-US/docs/Web/API/Document/animationend_event)
    3.  [`animationiteration`](https://developer.mozilla.org/en-US/docs/Web/API/Document/animationiteration_event)
    4.  [`animationstart`](https://developer.mozilla.org/en-US/docs/Web/API/Document/animationstart_event)
    5.  [`copy`](https://developer.mozilla.org/en-US/docs/Web/API/Document/copy_event)
    6.  [`cut`](https://developer.mozilla.org/en-US/docs/Web/API/Document/cut_event)
    7.  [`DOMContentLoaded`](https://developer.mozilla.org/en-US/docs/Web/API/Document/DOMContentLoaded_event)
    8.  [`drag`](https://developer.mozilla.org/en-US/docs/Web/API/Document/drag_event)
    9.  [`dragend`](https://developer.mozilla.org/en-US/docs/Web/API/Document/dragend_event)
    10. [`dragenter`](https://developer.mozilla.org/en-US/docs/Web/API/Document/dragenter_event)
    11. [`dragleave`](https://developer.mozilla.org/en-US/docs/Web/API/Document/dragleave_event)
    12. [`dragover`](https://developer.mozilla.org/en-US/docs/Web/API/Document/dragover_event)
    13. [`dragstart`](https://developer.mozilla.org/en-US/docs/Web/API/Document/dragstart_event)
    14. [`drop`](https://developer.mozilla.org/en-US/docs/Web/API/Document/drop_event)
    15. [`fullscreenchange`](https://developer.mozilla.org/en-US/docs/Web/API/Document/fullscreenchange_event)
    16. [`fullscreenerror`](https://developer.mozilla.org/en-US/docs/Web/API/Document/fullscreenerror_event)
    17. [`gotpointercapture`](https://developer.mozilla.org/en-US/docs/Web/API/Document/gotpointercapture_event)
    18. [`keydown`](https://developer.mozilla.org/en-US/docs/Web/API/Document/keydown_event)
    19. [`keypress`](https://developer.mozilla.org/en-US/docs/Web/API/Document/keypress_event)
    20. [`keyup`](https://developer.mozilla.org/en-US/docs/Web/API/Document/keyup_event)
    21. [`lostpointercapture`](https://developer.mozilla.org/en-US/docs/Web/API/Document/lostpointercapture_event)
    22. [`paste`](https://developer.mozilla.org/en-US/docs/Web/API/Document/paste_event)
    23. [`pointercancel`](https://developer.mozilla.org/en-US/docs/Web/API/Document/pointercancel_event)
    24. [`pointerdown`](https://developer.mozilla.org/en-US/docs/Web/API/Document/pointerdown_event)
    25. [`pointerenter`](https://developer.mozilla.org/en-US/docs/Web/API/Document/pointerenter_event)
    26. [`pointerleave`](https://developer.mozilla.org/en-US/docs/Web/API/Document/pointerleave_event)
    27. [`pointerlockchange`](https://developer.mozilla.org/en-US/docs/Web/API/Document/pointerlockchange_event)
    28. [`pointerlockerror`](https://developer.mozilla.org/en-US/docs/Web/API/Document/pointerlockerror_event)
    29. [`pointermove`](https://developer.mozilla.org/en-US/docs/Web/API/Document/pointermove_event)
    30. [`pointerout`](https://developer.mozilla.org/en-US/docs/Web/API/Document/pointerout_event)
    31. [`pointerover`](https://developer.mozilla.org/en-US/docs/Web/API/Document/pointerover_event)
    32. [`pointerup`](https://developer.mozilla.org/en-US/docs/Web/API/Document/pointerup_event)
    33. [`readystatechange`](https://developer.mozilla.org/en-US/docs/Web/API/Document/readystatechange_event)
    34. [`scroll`](https://developer.mozilla.org/en-US/docs/Web/API/Document/scroll_event)
    35. [`selectionchange`](https://developer.mozilla.org/en-US/docs/Web/API/Document/selectionchange_event)
    36. [`selectstart`](https://developer.mozilla.org/en-US/docs/Web/API/Document/selectstart_event)
    37. [`touchcancel`](https://developer.mozilla.org/en-US/docs/Web/API/Document/touchcancel_event)
    38. [`touchend`](https://developer.mozilla.org/en-US/docs/Web/API/Document/touchend_event)
    39. [`touchmove`](https://developer.mozilla.org/en-US/docs/Web/API/Document/touchmove_event)
    40. [`touchstart`](https://developer.mozilla.org/en-US/docs/Web/API/Document/touchstart_event)
    41. [`transitioncancel`](https://developer.mozilla.org/en-US/docs/Web/API/Document/transitioncancel_event)
    42. [`transitionend`](https://developer.mozilla.org/en-US/docs/Web/API/Document/transitionend_event)
    43. [`transitionrun`](https://developer.mozilla.org/en-US/docs/Web/API/Document/transitionrun_event)
    44. [`transitionstart`](https://developer.mozilla.org/en-US/docs/Web/API/Document/transitionstart_event)
    45. [`visibilitychange`](https://developer.mozilla.org/en-US/docs/Web/API/Document/visibilitychange_event)
    46. [`wheel`](https://developer.mozilla.org/en-US/docs/Web/API/Document/wheel_event)
7.  Inheritance:
    1.  [`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node)
    2.  [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)
8.  Related pages for DOM
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
    25. [`DOMPoint`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPoint)
    26. [`DOMPointInit`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPointInit)
    27. [`DOMPointReadOnly`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPointReadOnly)
    28. [`DOMRect`](https://developer.mozilla.org/en-US/docs/Web/API/DOMRect)
    29. [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString)
    30. [`DOMTimeStamp`](https://developer.mozilla.org/en-US/docs/Web/API/DOMTimeStamp)
    31. [`DOMTokenList`](https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList)
    32. [`DOMUserData`](https://developer.mozilla.org/en-US/docs/Web/API/DOMUserData)
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
