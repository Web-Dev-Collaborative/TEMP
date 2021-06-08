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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest" class="breadcrumb-current-page"><span data-property="name">XMLHttpRequest</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Constructor](#constructor)
-   [Properties](#properties)
-   [Methods](#methods)
-   [Events](#events)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

XMLHttpRequest
==============

<span class="seoSummary">`XMLHttpRequest` (XHR) objects are used to interact with servers. You can retrieve data from a URL without having to do a full page refresh. This enables a Web page to update just part of a page without disrupting what the user is doing.</span> `XMLHttpRequest` is used heavily in [AJAX](https://developer.mozilla.org/en-US/docs/Glossary/AJAX) programming.

Despite its name, `XMLHttpRequest` can be used to retrieve any type of data, not just XML.

If your communication needs to involve receiving event data or message data from a server, consider using [server-sent events](https://developer.mozilla.org/en-US/docs/Web/API/Server-sent_events) through the [`EventSource`](https://developer.mozilla.org/en-US/docs/Web/API/EventSource) interface. For full-duplex communication, [WebSockets](https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API) may be a better choice.

**Note:** This feature is available in [Web Workers](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API), except for [Service Workers](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API)

[Constructor](#constructor "Permalink to Constructor")
------------------------------------------------------

[`XMLHttpRequest()`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/XMLHttpRequest "XMLHttpRequest()")  
The constructor initializes an `XMLHttpRequest`. It must be called before any other method calls.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

*This interface also inherits properties of [`XMLHttpRequestEventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequestEventTarget) and of [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget).*

[`XMLHttpRequest.onreadystatechange`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/onreadystatechange)  
An [Event handler](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) that is called whenever the `readyState` attribute changes.

[`XMLHttpRequest.readyState`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/readyState) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns an `unsigned short`, the state of the request.

[`XMLHttpRequest.response`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/response) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer), [`Blob`](https://developer.mozilla.org/en-US/docs/Web/API/Blob), [`Document`](https://developer.mozilla.org/en-US/docs/Web/API/Document), JavaScript object, or a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString), depending on the value of [`XMLHttpRequest.responseType`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/responseType), that contains the response entity body.

[`XMLHttpRequest.responseText`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/responseText) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) that contains the response to the request as text, or `null` if the request was unsuccessful or has not yet been sent.

[`XMLHttpRequest.responseType`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/responseType)  
Is an enumerated value that defines the response type.

[`XMLHttpRequest.responseURL`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/responseURL) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the serialized URL of the response or the empty string if the URL is null.

[`XMLHttpRequest.responseXML`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/responseXML) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`Document`](https://developer.mozilla.org/en-US/docs/Web/API/Document) containing the response to the request, or `null` if the request was unsuccessful, has not yet been sent, or cannot be parsed as XML or HTML. Not available in workers.

[`XMLHttpRequest.status`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/status) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns an `unsigned short` with the status of the response of the request.

[`XMLHttpRequest.statusText`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/statusText) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) containing the response string returned by the HTTP server. Unlike [`XMLHttpRequest.status`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/status), this includes the entire text of the response message ("`200 OK`", for example).

#### Note

According to the HTTP/2 specification (<a href="https://http2.github.io/http2-spec/#rfc.section.8.1.2.4" class="external">8.1.2.4</a> <a href="https://http2.github.io/http2-spec/#HttpResponse" class="external">Response Pseudo-Header Fields</a>), HTTP/2 does not define a way to carry the version or reason phrase that is included in an HTTP/1.1 status line.

[`XMLHttpRequest.timeout`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/timeout)  
Is an `unsigned long` representing the number of milliseconds a request can take before automatically being terminated.

<span class="page-not-created">`XMLHttpRequestEventTarget.ontimeout`</span>  
Is an [Event handler](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) that is called whenever the request times out.

[`XMLHttpRequest.upload`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/upload) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Is an <span class="page-not-created">`XMLHttpRequestUpload`</span>, representing the upload process.

[`XMLHttpRequest.withCredentials`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/withCredentials)  
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that indicates whether or not cross-site `Access-Control` requests should be made using credentials such as cookies or authorization headers.

### [Non-standard properties](#non-standard_properties "Permalink to Non-standard properties")

[`XMLHttpRequest.channel`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/channel)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
The channel used by the object when performing the request.

[`XMLHttpRequest.mozAnon`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/mozAnon)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Is a boolean. If true, the request will be sent without cookie and authentication headers.

[`XMLHttpRequest.mozSystem`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/mozSystem)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Is a boolean. If true, the same origin policy will not be enforced on the request.

[`XMLHttpRequest.mozBackgroundRequest`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/mozBackgroundRequest)  
Is a boolean. It indicates whether or not the object represents a background service request.

[`XMLHttpRequest.mozResponseArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/mozResponseArrayBuffer) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
[`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer). The response to the request, as a JavaScript typed array.

[`XMLHttpRequest.multipart`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/multipart)   
**This Gecko-only feature, a boolean, was removed in Firefox/Gecko 22.** Please use [Server-Sent Events](https://developer.mozilla.org/en-US/docs/Web/API/Server-sent_events), [Web Sockets](https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API), or `responseText` from progress events instead.

### [Event handlers](#event_handlers "Permalink to Event handlers")

`onreadystatechange` as a property of the `XMLHttpRequest` instance is supported in all browsers.

Since then, a number of additional `on*` event handler properties have been implemented in various browsers (`onload`, `onerror`, `onprogress`, etc.). See [Using XMLHttpRequest](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/Using_XMLHttpRequest).

More recent browsers, including Firefox, also support listening to the `XMLHttpRequest` events via standard [`addEventListener()`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener "addEventListener()") APIs in addition to setting `on*` properties to a handler function.

[Methods](#methods "Permalink to Methods")
------------------------------------------

[`XMLHttpRequest.abort()`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/abort)  
Aborts the request if it has already been sent.

[`XMLHttpRequest.getAllResponseHeaders()`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/getAllResponseHeaders)  
Returns all the response headers, separated by [CRLF](https://developer.mozilla.org/en-US/docs/Glossary/CRLF), as a string, or `null` if no response has been received.

[`XMLHttpRequest.getResponseHeader()`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/getResponseHeader)  
Returns the string containing the text of the specified header, or `null` if either the response has not yet been received or the header doesn't exist in the response.

[`XMLHttpRequest.open()`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/open)  
Initializes a request.

[`XMLHttpRequest.overrideMimeType()`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/overrideMimeType)  
Overrides the MIME type returned by the server.

[`XMLHttpRequest.send()`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/send)  
Sends the request. If the request is asynchronous (which is the default), this method returns as soon as the request is sent.

[`XMLHttpRequest.setRequestHeader()`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/setRequestHeader)  
Sets the value of an HTTP request header. You must call `setRequestHeader()`after [`open()`](#open), but before `send()`.

[Events](#events "Permalink to Events")
---------------------------------------

[`abort`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/abort_event "abort")  
Fired when a request has been aborted, for example because the program called [`XMLHttpRequest.abort()`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/abort).  
Also available via the [`onabort`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequestEventTarget/onabort "onabort") property.

[`error`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/error_event "error")  
Fired when the request encountered an error.  
Also available via the [`onerror`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequestEventTarget/onerror "onerror") property.

[`load`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/load_event "load")  
Fired when an [`XMLHttpRequest`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest) transaction completes successfully.  
Also available via the [`onload`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequestEventTarget/onload "onload") property.

[`loadend`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/loadend_event "loadend")  
Fired when a request has completed, whether successfully (after [`load`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/load_event "load")) or unsuccessfully (after [`abort`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/abort_event "abort") or [`error`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/error_event "error")).  
Also available via the <span class="page-not-created">`onloadend`</span> property.

[`loadstart`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/loadstart_event "loadstart")  
Fired when a request has started to load data.  
Also available via the [`onloadstart`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequestEventTarget/onloadstart "onloadstart") property.

[`progress`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/progress_event "progress")  
Fired periodically when a request receives more data.  
Also available via the [`onprogress`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequestEventTarget/onprogress "onprogress") property.

[`timeout`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/timeout_event "timeout")  
Fired when progress is terminated due to preset time expiring.  
Also available via the <span class="page-not-created">`ontimeout`</span> property.

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://xhr.spec.whatwg.org/" class="external" title="The &#39;XMLHttpRequest&#39; specification">XMLHttpRequest</a></td><td><span class="spec-living">Living Standard</span></td><td>Live standard, latest version</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [`XMLSerializer`](https://developer.mozilla.org/en-US/docs/Web/API/XMLSerializer): Serializing a DOM tree into XML
-   MDN tutorials covering `XMLHttpRequest`:
    -   [Ajax — Getting Started](https://developer.mozilla.org/en-US/docs/Web/Guide/AJAX/Getting_Started)
    -   [Using XMLHttpRequest](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/Using_XMLHttpRequest)
    -   [HTML in XMLHttpRequest](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/HTML_in_XMLHttpRequest)
    -   [Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API "Fetch API")
-   <a href="https://www.html5rocks.com/en/tutorials/file/xhr2/" class="external">HTML5 Rocks — New Tricks in XMLHttpRequest2</a>
-   Feature-Policy directive [`sync-xhr`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy/sync-xhr)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/xmlhttprequest/index.html "Folder: en-us/web/api/xmlhttprequest (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FXMLHttpRequest%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fxmlhttprequest%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FXMLHttpRequest%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fxmlhttprequest%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F04853f63c112e0929d9502f1884f3c99149f75cc%0A*+Document+last+modified%3A+2021-06-01T06%3A47%3A24.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22XMLHttpRequest%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Jun 1, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/contributors.txt)

Change your languageSelect your preferred language English (US)DeutschEspañolFrançais日本語한국어PolskiPortuguês (do Brasil)Русский中文 (简体)正體中文 (繁體)

Change language

#### Related Topics

1.  **[XMLHttpRequest](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest)**
2.  Guides
    1.  [Using XMLHttpRequest](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/Using_XMLHttpRequest)
    2.  [HTML in XMLHttpRequest](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/HTML_in_XMLHttpRequest)
    3.  [Using XMLHttpRequest in IE6](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/Using_XMLHttpRequest_in_IE6)
3.  Interfaces
    1.  [`FormData`](https://developer.mozilla.org/en-US/docs/Web/API/FormData)
    2.  [`XMLHttpRequest`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest)
    3.  [`XMLHttpRequestEventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequestEventTarget)
    4.  [`XMLHttpRequestUpload`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequestUpload)

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
