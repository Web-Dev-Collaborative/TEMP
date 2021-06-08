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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/URL" class="breadcrumb-current-page"><span data-property="name">URL</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Constructor](#constructor)
-   [Properties](#properties)
-   [Methods](#methods)
-   [Static methods](#static_methods)
-   [Usage notes](#usage_notes)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

URL
===

<span class="seoSummary">The **`URL`** interface is used to parse, construct, normalize, and encode [URLs](https://developer.mozilla.org/en-US/docs/Glossary/URL). It works by providing properties which allow you to easily read and modify the components of a URL.</span> You normally create a new `URL` object by specifying the URL as a string when calling its constructor, or by providing a relative URL and a base URL. You can then easily read the parsed components of the URL or make changes to the URL.

If a browser doesn't yet support the [`URL()`](https://developer.mozilla.org/en-US/docs/Web/API/URL/URL "URL()") constructor, you can access a URL object using the [`Window`](https://developer.mozilla.org/en-US/docs/Web/API/Window) interface's [`URL`](https://developer.mozilla.org/en-US/docs/Web/API/URL) property. Be sure to check to see if any of your target browsers require this to be prefixed.

**Note:** This feature is available in [Web Workers](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API)

[Constructor](#constructor "Permalink to Constructor")
------------------------------------------------------

[`new URL()`](https://developer.mozilla.org/en-US/docs/Web/API/URL/URL "new URL()")  
Creates and returns a `URL` object referencing the URL specified using an absolute URL string, or a relative URL string and a base URL string.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

[`hash`](https://developer.mozilla.org/en-US/docs/Web/API/URL/hash "hash")  
A [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString) containing a `'#'` followed by the fragment identifier of the URL.

[`host`](https://developer.mozilla.org/en-US/docs/Web/API/URL/host "host")  
A [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString) containing the domain (that is the *hostname*) followed by (if a port was specified) a `':'` and the *port* of the URL.

[`hostname`](https://developer.mozilla.org/en-US/docs/Web/API/URL/hostname "hostname")  
A [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString) containing the domain of the URL.

[`href`](https://developer.mozilla.org/en-US/docs/Web/API/URL/href "href")  
A stringifier that returns a [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString) containing the whole URL.

[`origin`](https://developer.mozilla.org/en-US/docs/Web/API/URL/origin "origin") <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString) containing the origin of the URL, that is its scheme, its domain and its port.

[`password`](https://developer.mozilla.org/en-US/docs/Web/API/URL/password "password")  
A [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString) containing the password specified before the domain name.

[`pathname`](https://developer.mozilla.org/en-US/docs/Web/API/URL/pathname "pathname")  
Is a [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString) containing an initial `'/'` followed by the path of the URL, not including the query string or fragment.

[`port`](https://developer.mozilla.org/en-US/docs/Web/API/URL/port "port")  
A [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString) containing the port number of the URL.

[`protocol`](https://developer.mozilla.org/en-US/docs/Web/API/URL/protocol "protocol")  
A [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString) containing the protocol scheme of the URL, including the final `':'`.

[`search`](https://developer.mozilla.org/en-US/docs/Web/API/URL/search "search")  
A [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString) indicating the URL's parameter string; if any parameters are provided, this string includes all of them, beginning with the leading `?` character.

[`searchParams`](https://developer.mozilla.org/en-US/docs/Web/API/URL/searchParams "searchParams") <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
A [`URLSearchParams`](https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams) object which can be used to access the individual query parameters found in `search`.

[`username`](https://developer.mozilla.org/en-US/docs/Web/API/URL/username "username")  
A [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString) containing the username specified before the domain name.

[Methods](#methods "Permalink to Methods")
------------------------------------------

[`toString()`](https://developer.mozilla.org/en-US/docs/Web/API/URL/toString "toString()")  
Returns a [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString) containing the whole URL. It is a synonym for [`URL.href`](https://developer.mozilla.org/en-US/docs/Web/API/URL/href), though it can't be used to modify the value.

[`toJSON()`](https://developer.mozilla.org/en-US/docs/Web/API/URL/toJSON "toJSON()")  
Returns a [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString) containing the whole URL. It returns the same string as the `href` property.

[Static methods](#static_methods "Permalink to Static methods")
---------------------------------------------------------------

[`createObjectURL()`](https://developer.mozilla.org/en-US/docs/Web/API/URL/createObjectURL "createObjectURL()")  
Returns a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) containing a unique blob URL, that is a URL with `blob:` as its scheme, followed by an opaque string uniquely identifying the object in the browser.

[`revokeObjectURL()`](https://developer.mozilla.org/en-US/docs/Web/API/URL/revokeObjectURL "revokeObjectURL()")  
Revokes an object URL previously created using [`URL.createObjectURL()`](https://developer.mozilla.org/en-US/docs/Web/API/URL/createObjectURL).

[Usage notes](#usage_notes "Permalink to Usage notes")
------------------------------------------------------

The constructor takes a `url` parameter, and an optional `base` parameter to use as a base if the `url` parameter is a relative URL:

    const url = new URL('../cats', 'http://www.example.com/dogs');
    console.log(url.hostname); // "www.example.com"
    console.log(url.pathname); // "/cats"

URL properties can be set to construct the URL:

    url.hash = 'tabby';
    console.log(url.href); // "http://www.example.com/cats#tabby"

URLs are encoded according to the rules found in <a href="https://tools.ietf.org/html/rfc3986" class="external">RFC 3986</a>. For instance:

    url.pathname = 'démonstration.html';
    console.log(url.href); // "http://www.example.com/d%C3%A9monstration.html"

The [`URLSearchParams`](https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams) interface can be used to build and manipulate the URL query string.

To get the search params from the current window's URL, you can do this:

    // https://some.site/?id=123
    const parsedUrl = new URL(window.location.href);
    console.log(parsedUrl.searchParams.get("id")); // "123"

The [`toString()`](https://developer.mozilla.org/en-US/docs/Web/API/URL/toString "toString()") method of `URL` just returns the value of the [`href`](https://developer.mozilla.org/en-US/docs/Web/API/URL/href "href") property, so the constructor can be used to normalize and encode a URL directly.

    const response = await fetch(new URL('http://www.example.com/démonstration.html'));

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/FileAPI/#creating-revoking" class="external">File API<br />
<span class="small">The definition of 'URL' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Added the static methods <code>URL.createObjectURL()</code> and <code>URL.revokeObjectURL</code><code>()</code>.</td></tr><tr class="even"><td><a href="https://url.spec.whatwg.org/#api" class="external">URL<br />
<span class="small">The definition of 'API' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition (implements <code>URLUtils</code>).</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   A polyfill of `URL` is available in <a href="https://github.com/zloirock/core-js#url-and-urlsearchparams" class="external"><code>core-js</code></a>
-   [URL API](https://developer.mozilla.org/en-US/docs/Web/API/URL_API)
-   [What is a URL?](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_URL)
-   Property to obtain a `URL` object: [`URL`](https://developer.mozilla.org/en-US/docs/Web/API/URL).
-   [`URLSearchParams`](https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams).

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/url/index.html "Folder: en-us/web/api/url (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FURL%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Furl%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FURL%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Furl%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F753712510ce0974a3fc1483a9e8820d85721d09a%0A*+Document+last+modified%3A+2021-05-31T16%3A29%3A13.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22URL%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/URL/contributors.txt)

Change your languageSelect your preferred language English (US)DeutschEspañolFrançais日本語한국어Português (do Brasil)Русский中文 (简体)正體中文 (繁體)

Change language

#### Related Topics

1.  **[URL API](https://developer.mozilla.org/en-US/docs/Web/API/URL_API)**
2.  **[`URL`](https://developer.mozilla.org/en-US/docs/Web/API/URL)**
3.  Constructor
    1.  [`URL()`](https://developer.mozilla.org/en-US/docs/Web/API/URL/URL)
4.  Properties
    1.  [`hash`](https://developer.mozilla.org/en-US/docs/Web/API/URL/hash)
    2.  [`host`](https://developer.mozilla.org/en-US/docs/Web/API/URL/host)
    3.  [`hostname`](https://developer.mozilla.org/en-US/docs/Web/API/URL/hostname)
    4.  [`href`](https://developer.mozilla.org/en-US/docs/Web/API/URL/href)
    5.  [`origin`](https://developer.mozilla.org/en-US/docs/Web/API/URL/origin)
    6.  [`password`](https://developer.mozilla.org/en-US/docs/Web/API/URL/password)
    7.  [`pathname`](https://developer.mozilla.org/en-US/docs/Web/API/URL/pathname)
    8.  [`port`](https://developer.mozilla.org/en-US/docs/Web/API/URL/port)
    9.  [`protocol`](https://developer.mozilla.org/en-US/docs/Web/API/URL/protocol)
    10. [`search`](https://developer.mozilla.org/en-US/docs/Web/API/URL/search)
    11. [`searchParams`](https://developer.mozilla.org/en-US/docs/Web/API/URL/searchParams)
    12. [`username`](https://developer.mozilla.org/en-US/docs/Web/API/URL/username)
5.  Methods
    1.  [`createObjectURL()`](https://developer.mozilla.org/en-US/docs/Web/API/URL/createObjectURL)
    2.  [`revokeObjectURL()`](https://developer.mozilla.org/en-US/docs/Web/API/URL/revokeObjectURL)
    3.  [`toJSON()`](https://developer.mozilla.org/en-US/docs/Web/API/URL/toJSON)
    4.  [`toString()`](https://developer.mozilla.org/en-US/docs/Web/API/URL/toString)
6.  Related pages for URL API
    1.  [`URLSearchParams`](https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams)

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
