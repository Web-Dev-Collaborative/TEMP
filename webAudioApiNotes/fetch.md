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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope" class="breadcrumb-penultimate"><span data-property="name">WindowOrWorkerGlobalScope</span></a>
4.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/fetch" class="breadcrumb-current-page"><span data-property="name">WindowOrWorkerGlobalScope.fetch()</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Syntax](#syntax)
-   [Examples](#examples)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

WindowOrWorkerGlobalScope.fetch()
=================================

<span class="seoSummary">The `fetch()` method of the [`WindowOrWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope) mixin starts the process of fetching a resource from the network, returning a promise which is fulfilled once the response is available.</span> The promise resolves to the [`Response`](https://developer.mozilla.org/en-US/docs/Web/API/Response) object representing the response to your request. The promise *does not* reject on HTTP errors — it only rejects on network errors. You must use `then` handlers to check for HTTP errors.

`WindowOrWorkerGlobalScope` is implemented by both [`Window`](https://developer.mozilla.org/en-US/docs/Web/API/Window) and [`WorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope), which means that the `fetch()` method is available in pretty much any context in which you might want to fetch resources.

A [`fetch()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/fetch "fetch()") promise only rejects when a network error is encountered (which is usually when there’s a permissions issue or similar). A [`fetch()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/fetch "fetch()") promise *does not* reject on HTTP errors (`404`, etc.). Instead, a `then()` handler must check the [`Response.ok`](https://developer.mozilla.org/en-US/docs/Web/API/Response/ok) and/or [`Response.status`](https://developer.mozilla.org/en-US/docs/Web/API/Response/status) properties.

The `fetch()` method is controlled by the `connect-src` directive of [Content Security Policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy) rather than the directive of the resources it's retrieving.

**Note**: The `fetch()` method's parameters are identical to those of the [`Request()`](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request "Request()") constructor.

[Syntax](#syntax "Permalink to Syntax")
---------------------------------------

    const fetchResponsePromise = fetch(resource [, init])

### [Parameters](#parameters "Permalink to Parameters")

`resource`  
This defines the resource that you wish to fetch. This can either be:

-   A string or any other object with a [stringifier](https://developer.mozilla.org/en-US/docs/MDN/Contribute/Howto/Write_an_API_reference/Information_contained_in_a_WebIDL_file#stringifiers) — including a [`URL`](https://developer.mozilla.org/en-US/docs/Web/API/URL) object — that provides the URL of the resource you want to fetch.
-   A [`Request`](https://developer.mozilla.org/en-US/docs/Web/API/Request) object.

`init` <span class="badge inline optional">Optional</span>  
An object containing any custom settings that you want to apply to the request. The possible options are:

`method`  
The request method, e.g., `GET`, `POST`. Note that the [`Origin`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Origin) header is not set on Fetch requests with a method of [`HEAD`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/HEAD) or [`GET`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/GET).  
(This behavior was corrected in Firefox 65 — see <a href="https://bugzilla.mozilla.org/show_bug.cgi?id=1508661" class="external">bug 1508661</a>).

`headers`  
Any headers you want to add to your request, contained within a [`Headers`](https://developer.mozilla.org/en-US/docs/Web/API/Headers) object or an object literal with [`ByteString`](https://developer.mozilla.org/en-US/docs/Web/API/ByteString) values. Note that [some names are forbidden](https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name).

`body`  
Any body that you want to add to your request: this can be a [`Blob`](https://developer.mozilla.org/en-US/docs/Web/API/Blob), [`BufferSource`](https://developer.mozilla.org/en-US/docs/Web/API/BufferSource), [`FormData`](https://developer.mozilla.org/en-US/docs/Web/API/FormData), [`URLSearchParams`](https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams), [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString), or [`ReadableStream`](https://developer.mozilla.org/en-US/docs/Web/API/ReadableStream) object. Note that a request using the `GET` or `HEAD` method cannot have a body.

`mode`  
The mode you want to use for the request, e.g., `cors`, `no-cors`, or `same-origin`.

`credentials`  
Controls what browsers do with credentials ([cookies](https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies), [HTTP authentication](https://developer.mozilla.org/en-US/docs/Web/HTTP/Authentication) entries, and TLS client certificates). Must be one of the following strings:

`omit`  
Tells browsers to exclude credentials from the request, and ignore any credentials sent back in the response (e.g., any [`Set-Cookie`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Set-Cookie) header).

`same-origin`  
Tells browsers to include credentials with requests to same-origin URLs, and use any credentials sent back in responses from same-origin URLs.

`include`  
Tells browsers to include credentials in both same- and cross-origin requests, and always use any credentials sent back in responses.

#### Note

Credentials may be included in simple and "final" cross-origin requests, but should not be included in [CORS preflight requests](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS#preflight_requests_and_credentials).

`cache`  
A string indicating how the request will interact with the browser’s [HTTP cache](https://developer.mozilla.org/en-US/docs/Web/HTTP/Caching). The possible values, `default`, `no-store`, `reload`, `no-cache`, `force-cache`, and `only-if-cached`, are documented in the article for the [`cache`](https://developer.mozilla.org/en-US/docs/Web/API/Request/cache "cache") property of the [`Request`](https://developer.mozilla.org/en-US/docs/Web/API/Request) object.

`redirect`  
How to handle a `redirect` response:

-   `follow`: Automatically follow redirects. Unless otherwise stated the redirect mode is set to `follow`
-   `error`: Abort with an error if a redirect occurs.
-   `manual`: Caller intends to process the response in another context.  
    See <a href="https://fetch.spec.whatwg.org/#requests" class="external">WHATWG fetch standard</a> for more information.

`referrer`  
A [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString) specifying the referrer of the request. This can be a same-origin URL, `about:client`, or an empty string.

`referrerPolicy`  
Specifies the <a href="https://w3c.github.io/webappsec-referrer-policy/#referrer-policies" class="external">referrer policy</a> to use for the request. May be one of `no-referrer`, `no-referrer-when-downgrade`, `same-origin`, `origin`, `strict-origin`, `origin-when-cross-origin`, `strict-origin-when-cross-origin`, or `unsafe-url`.

`integrity`  
Contains the [subresource integrity](https://developer.mozilla.org/en-US/docs/Web/Security/Subresource_Integrity) value of the request (e.g., `sha256-BpfBw7ivV8q2jLiT13fxDYAe2tJllusRSZ273h2nFSE=`).

`keepalive`  
The `keepalive` option can be used to allow the request to outlive the page. Fetch with the `keepalive` flag is a replacement for the [`Navigator.sendBeacon()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/sendBeacon) API.

`signal`  
An [`AbortSignal`](https://developer.mozilla.org/en-US/docs/Web/API/AbortSignal) object instance; allows you to communicate with a fetch request and abort it if desired via an [`AbortController`](https://developer.mozilla.org/en-US/docs/Web/API/AbortController).

### [Return value](#return_value "Permalink to Return value")

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to a [`Response`](https://developer.mozilla.org/en-US/docs/Web/API/Response) object.

### [Exceptions](#exceptions "Permalink to Exceptions")

`AbortError`  
The request was aborted due to a call to the [`AbortController`](https://developer.mozilla.org/en-US/docs/Web/API/AbortController) [`abort()`](https://developer.mozilla.org/en-US/docs/Web/API/AbortController/abort "abort()") method.

`TypeError`  
The specified URL string includes user credentials. This information should instead be provided using an [`Authorization`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Authorization) header.

[Examples](#examples "Permalink to Examples")
---------------------------------------------

In our <a href="https://github.com/mdn/fetch-examples/tree/master/fetch-request" class="external">Fetch Request example</a> (see <a href="https://mdn.github.io/fetch-examples/fetch-request/" class="external">Fetch Request live</a>) we create a new [`Request`](https://developer.mozilla.org/en-US/docs/Web/API/Request) object using the relevant constructor, then fetch it using a `fetch()` call. Since we are fetching an image, we run [`Body.blob()`](https://developer.mozilla.org/en-US/docs/Web/API/Body/blob) on the response to give it the proper MIME type so it will be handled properly, then create an Object URL of it and display it in an [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) element.

    const myImage = document.querySelector('img');

    let myRequest = new Request('flowers.jpg');

    fetch(myRequest)
    .then(function(response) {
      if (!response.ok) {
        throw new Error(`HTTP error! status: ${response.status}`);
      }
      return response.blob();
    })
    .then(function(response) {
      let objectURL = URL.createObjectURL(response);
      myImage.src = objectURL;
    });

In the <a href="https://github.com/mdn/fetch-examples/blob/master/fetch-with-init-then-request/index.html" class="external">Fetch with init then Request example</a> (see <a href="https://mdn.github.io/fetch-examples/fetch-with-init-then-request/" class="external">Fetch Request init live</a>), we do the same thing except that we pass in an `init` object when we invoke `fetch()`:

    const myImage = document.querySelector('img');

    let myHeaders = new Headers();
    myHeaders.append('Accept', 'image/jpeg');

    const myInit = {
      method: 'GET',
      headers: myHeaders,
      mode: 'cors',
      cache: 'default'
    };

    let myRequest = new Request('flowers.jpg');

    fetch(myRequest, myInit).then(function(response) {
      // ...
    });

You could also pass the `init` object in with the `Request` constructor to get the same effect:

    let myRequest = new Request('flowers.jpg', myInit);

You can also use an object literal as `headers` in `init`.

    const myInit = {
      method: 'GET',
      headers: {
        'Accept': 'image/jpeg'
      },
      mode: 'cors',
      cache: 'default'
    };

    let myRequest = new Request('flowers.jpg', myInit);

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#fetch-method" class="external">Fetch<br />
<span class="small">The definition of 'fetch()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Defined in a <code>WindowOrWorkerGlobalScope</code> partial in the newest spec.</td></tr><tr class="even"><td><a href="https://fetch.spec.whatwg.org/#dom-global-fetch" class="external">Fetch<br />
<span class="small">The definition of 'fetch()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr><tr class="odd"><td><a href="https://w3c.github.io/webappsec-credential-management/" class="external" title="The &#39;Credential Management Level 1&#39; specification">Credential Management Level 1</a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds <a href="https://developer.mozilla.org/en-US/docs/Web/API/FederatedCredential"><code>FederatedCredential</code></a> or <a href="https://developer.mozilla.org/en-US/docs/Web/API/PasswordCredential"><code>PasswordCredential</code></a> instance as a possible value for <code>init.credentials</code>.</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API)
-   [ServiceWorker API](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API)
-   [HTTP access control (CORS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
-   [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/windoworworkerglobalscope/fetch/index.html "Folder: en-us/web/api/windoworworkerglobalscope/fetch (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWindowOrWorkerGlobalScope%2Ffetch%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fwindoworworkerglobalscope%2Ffetch%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWindowOrWorkerGlobalScope%2Ffetch%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fwindoworworkerglobalscope%2Ffetch%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F94c536f9b3a50303a85e7963a4ff4958d1aec382%0A*+Document+last+modified%3A+2021-05-31T17%3A13%3A02.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22WindowOrWorkerGlobalScope.fetch%28%29%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/fetch/contributors.txt)

Change your languageSelect your preferred language English (US)EspañolFrançais日本語Português (do Brasil)Русский中文 (简体)

Change language

#### Related Topics

1.  **[Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API)**
2.  **[`WindowOrWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope)**
3.  Properties
    1.  [`caches`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/caches)
    2.  [`crossOriginIsolated`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/crossOriginIsolated)
    3.  [`indexedDB`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/indexedDB)
    4.  [`isSecureContext`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/isSecureContext)
    5.  [`origin`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/origin)
4.  Methods
    1.  [`atob()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/atob)
    2.  [`btoa()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/btoa)
    3.  [`clearInterval()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/clearInterval)
    4.  [`clearTimeout()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/clearTimeout)
    5.  [`createImageBitmap()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/createImageBitmap)
    6.  *`fetch()`*
    7.  [`queueMicrotask()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/queueMicrotask)
    8.  [`setInterval()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setInterval)
    9.  [`setTimeout()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setTimeout)
5.  Implemented by:
    1.  [`Window`](https://developer.mozilla.org/en-US/docs/Web/API/Window)
    2.  [`WorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope)
6.  Related pages for Fetch API
    1.  [`Body`](https://developer.mozilla.org/en-US/docs/Web/API/Body)
    2.  [`Headers`](https://developer.mozilla.org/en-US/docs/Web/API/Headers)
    3.  [`Request`](https://developer.mozilla.org/en-US/docs/Web/API/Request)
    4.  [`Response`](https://developer.mozilla.org/en-US/docs/Web/API/Response)
    5.  [`WindowOrWorkerGlobalScope.fetch()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/fetch)

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
