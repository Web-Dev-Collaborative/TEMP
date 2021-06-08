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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/Worker" class="breadcrumb-penultimate"><span data-property="name">Worker</span></a>
4.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/Worker/Worker" class="breadcrumb-current-page"><span data-property="name">Worker()</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Syntax](#syntax)
-   [Examples](#examples)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

Worker()
========

The `Worker()` constructor creates a [`Worker`](https://developer.mozilla.org/en-US/docs/Web/API/Worker) object that executes the script at the specified URL. This script must obey the [same-origin policy](https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy "Same origin policy for JavaScript").

**Note**: that there is a disagreement among browser manufacturers about whether a data URI is of the same origin or not. Though Gecko 10.0 (Firefox 10.0 / Thunderbird 10.0 / SeaMonkey 2.7) and later accept data URIs, that's not the case in all other browsers.

[Syntax](#syntax "Permalink to Syntax")
---------------------------------------

    var myWorker = new Worker(aURL, options);

### [Parameters](#parameters "Permalink to Parameters")

*aURL*  
A [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString) representing the URL of the script the worker will execute. It must obey the same-origin policy.

*options* <span class="badge inline optional">Optional</span>  
An object containing option properties that can be set when creating the object instance. Available properties are as follows:

-   `type`: A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) specifying the type of worker to create. The value can be `classic` or `module`. If not specified, the default used is `classic`.
-   `credentials`: A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) specifying the type of credentials to use for the worker. The value can be `omit`, `same-origin`, or `include`. If not specified, or if type is `classic`, the default used is `omit` (no credentials required).
-   `name`: A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) specifying an identifying name for the [`DedicatedWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/DedicatedWorkerGlobalScope) representing the scope of the worker, which is mainly useful for debugging purposes.

### [Exceptions](#exceptions "Permalink to Exceptions")

-   A `SecurityError` is raised if the document is not allowed to start workers, e.g. if the URL has an invalid syntax or if the same-origin policy is violated.
-   A `NetworkError` is raised if the MIME type of the worker script is incorrect. It *should* always be `text/javascript` (for historical reasons [other JavaScript MIME types](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/MIME_types#javascript_types) may be accepted).
-   A `SyntaxError` is raised if *aURL* cannot be parsed.

[Examples](#examples "Permalink to Examples")
---------------------------------------------

The following code snippet shows creation of a [`Worker`](https://developer.mozilla.org/en-US/docs/Web/API/Worker) object using the `Worker()` constructor and subsequent usage of the object:

    var myWorker = new Worker('worker.js');

    first.onchange = function() {
      myWorker.postMessage([first.value,second.value]);
      console.log('Message posted to worker');
    }

For a full example, see our <a href="https://github.com/mdn/simple-web-worker" class="external external-icon">Basic dedicated worker example</a> (<a href="https://mdn.github.io/simple-web-worker/" class="external external-icon">run dedicated worker</a>).

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-worker" class="external">HTML Living Standard<br />
<span class="small">The definition of 'Worker()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

**Note**: A browser can be marked as providing full support for `Worker()` even though it does not support worker scripts written as modules. As of Mar 1, 2019, only <a href="https://web.dev/module-workers/" class="external">Chrome 80+</a> supports this feature, while <a href="https://bugzilla.mozilla.org/show_bug.cgi?id=1247687" class="external">Firefox has an open feature request</a>.  No other browsers are known to have support for production usage of worker scripts written as modules. Without that support, worker scripts written as modules and modules used by worker scripts have to be transpiled or otherwise converted to non-module code in order to run.

[See also](#see_also "Permalink to See also")
---------------------------------------------

The [`Worker`](https://developer.mozilla.org/en-US/docs/Web/API/Worker) interface it belongs to.

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/worker/worker/index.html "Folder: en-us/web/api/worker/worker (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWorker%2FWorker%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fworker%2Fworker%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWorker%2FWorker%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fworker%2Fworker%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F94c536f9b3a50303a85e7963a4ff4958d1aec382%0A*+Document+last+modified%3A+2021-05-31T17%3A13%3A02.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22Worker%28%29%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/Worker/Worker/contributors.txt)

Change your languageSelect your preferred language English (US)Français日本語Русский中文 (简体)

Change language

#### Related Topics

1.  **[Web Workers API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API)**
2.  **[`Worker`](https://developer.mozilla.org/en-US/docs/Web/API/Worker)**
3.  Constructor
    1.  *`Worker()`*
4.  Properties
    1.  [`onerror`](https://developer.mozilla.org/en-US/docs/Web/API/AbstractWorker/onerror)
    2.  [`onmessage`](https://developer.mozilla.org/en-US/docs/Web/API/Worker/onmessage)
    3.  [`onmessageerror`](https://developer.mozilla.org/en-US/docs/Web/API/Worker/onmessageerror)
5.  Methods
    1.  [`postMessage()`](https://developer.mozilla.org/en-US/docs/Web/API/Worker/postMessage)
    2.  [`terminate()`](https://developer.mozilla.org/en-US/docs/Web/API/Worker/terminate)
6.  Events
    1.  [`message`](https://developer.mozilla.org/en-US/docs/Web/API/Worker/message_event)
    2.  [`messageerror`](https://developer.mozilla.org/en-US/docs/Web/API/Worker/messageerror_event)
7.  Inheritance:
    1.  [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)
8.  Related pages for Web Workers API
    1.  [`AbstractWorker`](https://developer.mozilla.org/en-US/docs/Web/API/AbstractWorker)
    2.  [`ChromeWorker`](https://developer.mozilla.org/en-US/docs/Web/API/ChromeWorker)
    3.  [`DedicatedWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/DedicatedWorkerGlobalScope)
    4.  [`ServiceWorker`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorker)
    5.  [`SharedWorker`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorker)
    6.  [`SharedWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorkerGlobalScope)
    7.  [`WorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope)
    8.  [`WorkerLocation`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerLocation)
    9.  [`WorkerNavigator`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerNavigator)

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
