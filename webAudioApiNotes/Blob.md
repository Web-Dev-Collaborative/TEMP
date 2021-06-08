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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/Blob" class="breadcrumb-current-page"><span data-property="name">Blob</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Using blobs](#using_blobs)
-   [Constructor](#constructor)
-   [Instance properties](#instance_properties)
-   [Instance methods](#instance_methods)
-   [Examples](#examples)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

Blob
====

The **`Blob`** object represents a blob, which is a file-like object of immutable, raw data; they can be read as text or binary data, or converted into a [`ReadableStream`](https://developer.mozilla.org/en-US/docs/Web/API/ReadableStream) so its methods can be used for processing the data.

Blobs can represent data that isn't necessarily in a JavaScript-native format. The [`File`](https://developer.mozilla.org/en-US/docs/Web/API/File) interface is based on `Blob`, inheriting blob functionality and expanding it to support files on the user's system.

[Using blobs](#using_blobs "Permalink to Using blobs")
------------------------------------------------------

To construct a `Blob` from other non-blob objects and data, use the [`Blob()`](https://developer.mozilla.org/en-US/docs/Web/API/Blob/Blob "Blob()") constructor. To create a blob that contains a subset of another blob's data, use the [`slice()`](https://developer.mozilla.org/en-US/docs/Web/API/Blob/slice "slice()") method. To obtain a `Blob` object for a file on the user's file system, see the [`File`](https://developer.mozilla.org/en-US/docs/Web/API/File) documentation.

The APIs accepting `Blob` objects are also listed in the [`File`](https://developer.mozilla.org/en-US/docs/Web/API/File) documentation.

[Constructor](#constructor "Permalink to Constructor")
------------------------------------------------------

[`Blob()`](https://developer.mozilla.org/en-US/docs/Web/API/Blob/Blob "Blob()")  
Returns a newly created `Blob` object which contains a concatenation of all of the data in the array passed into the constructor.

[Instance properties](#instance_properties "Permalink to Instance properties")
------------------------------------------------------------------------------

[`Blob.prototype.size`](https://developer.mozilla.org/en-US/docs/Web/API/Blob/size) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
The size, in bytes, of the data contained in the `Blob` object.

[`Blob.prototype.type`](https://developer.mozilla.org/en-US/docs/Web/API/Blob/type) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
A string indicating the MIME type of the data contained in the `Blob`. If the type is unknown, this string is empty.

[Instance methods](#instance_methods "Permalink to Instance methods")
---------------------------------------------------------------------

[`Blob.prototype.arrayBuffer()`](https://developer.mozilla.org/en-US/docs/Web/API/Blob/arrayBuffer)  
Returns a promise that resolves with an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) containing the entire contents of the `Blob` as binary data.

[`Blob.prototype.slice()`](https://developer.mozilla.org/en-US/docs/Web/API/Blob/slice)  
Returns a new `Blob` object containing the data in the specified range of bytes of the blob on which it's called.

[`Blob.prototype.stream()`](https://developer.mozilla.org/en-US/docs/Web/API/Blob/stream)  
Returns a [`ReadableStream`](https://developer.mozilla.org/en-US/docs/Web/API/ReadableStream) that can be used to read the contents of the `Blob`.

[`Blob.prototype.text()`](https://developer.mozilla.org/en-US/docs/Web/API/Blob/text)  
Returns a promise that resolves with a [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString) containing the entire contents of the `Blob` interpreted as UTF-8 text.

[Examples](#examples "Permalink to Examples")
---------------------------------------------

### [Creating a blob](#creating_a_blob "Permalink to Creating a blob")

The [`Blob()`](https://developer.mozilla.org/en-US/docs/Web/API/Blob/Blob "Blob()") constructor can create blobs from other objects. For example, to construct a blob from a JSON string:

    const obj = {hello: 'world'};
    const blob = new Blob([JSON.stringify(obj, null, 2)], {type : 'application/json'});

### [Creating a URL representing the contents of a typed array](#creating_a_url_representing_the_contents_of_a_typed_array "Permalink to Creating a URL representing the contents of a typed array")

The following code creates a JavaScript [typed array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Typed_arrays) and creates a new `Blob` containing the typed array's data. It then calls [`URL.createObjectURL()`](https://developer.mozilla.org/en-US/docs/Web/API/URL/createObjectURL) to convert the blob into a [URL](https://developer.mozilla.org/en-US/docs/Glossary/URL).

#### HTML

    <p>This example creates a typed array containing the ASCII codes
       for the space character through the letter Z, then converts it
       to an object URL. A link to open that object URL is created.
       Click the link to see the decoded object URL.</p>

#### JavaScript

The main piece of this code for example purposes is the `typedArrayToURL()` function, which creates a `Blob` from the given typed array and returns an object URL for it. Having converted the data into an object URL, it can be used in a number of ways, including as the value of the [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) element's [`src`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#attr-src) attribute (assuming the data contains an image, of course).

    function typedArrayToURL(typedArray, mimeType) {
      return URL.createObjectURL(new Blob([typedArray.buffer], {type: mimeType}))
    }

    const bytes = new Uint8Array(59);

    for(let i = 0; i < 59; i++) {
      bytes[i] = 32 + i;
    }

    const url = typedArrayToURL(bytes, 'text/plain');

    const link = document.createElement('a');
    link.href = url;
    link.innerText = 'Open the array URL';

    document.body.appendChild(link);

#### Result

Click the link in the example to see the browser decode the object URL.

### [Extracting data from a blob](#extracting_data_from_a_blob "Permalink to Extracting data from a blob")

One way to read content from a `Blob` is to use a [`FileReader`](https://developer.mozilla.org/en-US/docs/Web/API/FileReader). The following code reads the content of a `Blob` as a typed array:

    const reader = new FileReader();
    reader.addEventListener('loadend', () => {
       // reader.result contains the contents of blob as a typed array
    });
    reader.readAsArrayBuffer(blob);

Another way to read content from a `Blob` is to use a [`Response`](https://developer.mozilla.org/en-US/docs/Web/API/Response). The following code reads the content of a `Blob` as text:

    const text = await (new Response(blob)).text();

Or by using [`Blob.prototype.text()`](https://developer.mozilla.org/en-US/docs/Web/API/Blob/text):

    const text = await blob.text();

By using other methods of `FileReader`, it is possible to read the contents of a Blob as a string or a data URL.

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/FileAPI/#blob-section" class="external">File API<br />
<span class="small">The definition of 'The <code>Blob</code> interface' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [`BlobBuilder`](https://developer.mozilla.org/en-US/docs/Web/API/BlobBuilder)
-   [`FileReader`](https://developer.mozilla.org/en-US/docs/Web/API/FileReader)
-   [`File`](https://developer.mozilla.org/en-US/docs/Web/API/File)
-   [`URL.createObjectURL`](https://developer.mozilla.org/en-US/docs/Web/API/URL/createObjectURL)
-   [Using files from web applications](https://developer.mozilla.org/en-US/docs/Web/API/File/Using_files_from_web_applications)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/blob/index.html "Folder: en-us/web/api/blob (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FBlob%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fblob%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FBlob%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fblob%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F591362776c1ef3ad42942777979939e511dd811f%0A*+Document+last+modified%3A+2021-05-29T03%3A45%3A05.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22Blob%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 29, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/Blob/contributors.txt)

Change your languageSelect your preferred language English (US)DeutschEspañolFrançais日本語한국어Português (do Brasil)Русский中文 (简体)正體中文 (繁體)

Change language

#### Related Topics

1.  **[`Blob`](https://developer.mozilla.org/en-US/docs/Web/API/Blob)**
2.  Constructor
    1.  [`Blob()`](https://developer.mozilla.org/en-US/docs/Web/API/Blob/Blob)
3.  Properties
    1.  [`size`](https://developer.mozilla.org/en-US/docs/Web/API/Blob/size)
    2.  [`type`](https://developer.mozilla.org/en-US/docs/Web/API/Blob/type)
4.  Methods
    1.  [`arrayBuffer()`](https://developer.mozilla.org/en-US/docs/Web/API/Blob/arrayBuffer)
    2.  [`slice()`](https://developer.mozilla.org/en-US/docs/Web/API/Blob/slice)
    3.  [`stream()`](https://developer.mozilla.org/en-US/docs/Web/API/Blob/stream)
    4.  [`text()`](https://developer.mozilla.org/en-US/docs/Web/API/Blob/text)
5.  Related pages for File API
    1.  [`File`](https://developer.mozilla.org/en-US/docs/Web/API/File)
    2.  [`FileList`](https://developer.mozilla.org/en-US/docs/Web/API/FileList)
    3.  [`FileReader`](https://developer.mozilla.org/en-US/docs/Web/API/FileReader)
    4.  [`FileReaderSync`](https://developer.mozilla.org/en-US/docs/Web/API/FileReaderSync)

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
