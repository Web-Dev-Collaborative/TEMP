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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/SharedWorker" class="breadcrumb-current-page"><span data-property="name">SharedWorker</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Constructors](#constructors)
-   [Properties](#properties)
-   [Methods](#methods)
-   [Example](#example)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

SharedWorker
============

The `SharedWorker` interface represents a specific kind of worker that can be *accessed* from several browsing contexts, such as several windows, iframes or even workers. They implement an interface different than dedicated workers and have a different global scope, [`SharedWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorkerGlobalScope).

**Note:** If SharedWorker can be accessed from several browsing contexts, all those browsing contexts must share the exact same origin (same protocol, host and port).

[Constructors](#constructors "Permalink to Constructors")
---------------------------------------------------------

[`SharedWorker()`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorker/SharedWorker "SharedWorker()")  
Creates a shared web worker that executes the script at the specified URL.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

*Inherits properties from its parent, [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget), and implements properties from [`AbstractWorker`](https://developer.mozilla.org/en-US/docs/Web/API/AbstractWorker).*

[`AbstractWorker.onerror`](https://developer.mozilla.org/en-US/docs/Web/API/AbstractWorker/onerror)  
Is an [`EventListener`](https://developer.mozilla.org/en-US/docs/Web/API/EventListener) that is called whenever an [`ErrorEvent`](https://developer.mozilla.org/en-US/docs/Web/API/ErrorEvent) of type `error` event occurs.

[`SharedWorker.port`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorker/port) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`MessagePort`](https://developer.mozilla.org/en-US/docs/Web/API/MessagePort) object used to communicate with and control the shared worker.

[Methods](#methods "Permalink to Methods")
------------------------------------------

*Inherits methods from its parent, [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget), and implements methods from [`AbstractWorker`](https://developer.mozilla.org/en-US/docs/Web/API/AbstractWorker).*

[Example](#example "Permalink to Example")
------------------------------------------

In our <a href="https://github.com/mdn/simple-shared-worker" class="external external-icon">Basic shared worker example</a> (<a href="https://mdn.github.io/simple-shared-worker/" class="external external-icon">run shared worker</a>), we have two HTML pages, each of which uses some JavaScript to perform a simple calculation. The different scripts are using the same worker file to perform the calculation — they can both access it, even if their pages are running inside different windows.

The following code snippet shows creation of a `SharedWorker` object using the [`SharedWorker()`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorker/SharedWorker "SharedWorker()") constructor. Both scripts contain this:

    var myWorker = new SharedWorker('worker.js');

Both scripts then access the worker through a [`MessagePort`](https://developer.mozilla.org/en-US/docs/Web/API/MessagePort) object created using the [`SharedWorker.port`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorker/port) property. If the onmessage event is attached using addEventListener, the port is manually started using its `start()` method:

    myWorker.port.start();

When the port is started, both scripts post messages to the worker and handle messages sent from it using `port.postMessage()` and `port.onmessage`, respectively:

    first.onchange = function() {
      myWorker.port.postMessage([first.value,second.value]);
      console.log('Message posted to worker');
    }

    second.onchange = function() {
      myWorker.port.postMessage([first.value,second.value]);
      console.log('Message posted to worker');
    }

    myWorker.port.onmessage = function(e) {
      result1.textContent = e.data;
      console.log('Message received from worker');
    }

Inside the worker we use the [`SharedWorkerGlobalScope.onconnect`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorkerGlobalScope/onconnect) handler to connect to the same port discussed above. The ports associated with that worker are accessible in the `connect` event's `ports` property — we then use [`MessagePort`](https://developer.mozilla.org/en-US/docs/Web/API/MessagePort) `start()` method to start the port, and the `onmessage` handler to deal with messages sent from the main threads.

    onconnect = function(e) {
      var port = e.ports[0];

      port.addEventListener('message', function(e) {
        var workerResult = 'Result: ' + (e.data[0] * e.data[1]);
        port.postMessage(workerResult);
      });

      port.start(); // Required when using addEventListener. Otherwise called implicitly by onmessage setter.
    }

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#sharedworker" class="external">HTML Living Standard<br />
<span class="small">The definition of 'SharedWorker' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="about:unknown" class="external" title="The &#39;Unknown&#39; specification">Unknown</a>.</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [`Worker`](https://developer.mozilla.org/en-US/docs/Web/API/Worker)
-   <a href="https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Using_web_workers" class="internal">Using web workers</a>

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/sharedworker/index.html "Folder: en-us/web/api/sharedworker (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FSharedWorker%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fsharedworker%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FSharedWorker%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fsharedworker%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F67eb075e2a8ab4f59f4e00496c5b89d7d8fcef16%0A*+Document+last+modified%3A+2021-06-04T09%3A24%3A31.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22SharedWorker%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Jun 4, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorker/contributors.txt)

Change your languageSelect your preferred language English (US)DeutschFrançais日本語한국어Português (do Brasil)Русский中文 (简体)

Change language

#### Related Topics

1.  **[Web Workers API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API)**
2.  **[`SharedWorker`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorker)**
3.  Constructor
    1.  [`SharedWorker()`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorker/SharedWorker)
4.  Properties
    1.  [`onerror`](https://developer.mozilla.org/en-US/docs/Web/API/AbstractWorker/onerror)
    2.  [`port`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorker/port)
5.  Inheritance:
    1.  [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)
6.  Related pages for Web Workers API
    1.  [`AbstractWorker`](https://developer.mozilla.org/en-US/docs/Web/API/AbstractWorker)
    2.  [`ChromeWorker`](https://developer.mozilla.org/en-US/docs/Web/API/ChromeWorker)
    3.  [`DedicatedWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/DedicatedWorkerGlobalScope)
    4.  [`ServiceWorker`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorker)
    5.  [`SharedWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorkerGlobalScope)
    6.  [`Worker`](https://developer.mozilla.org/en-US/docs/Web/API/Worker)
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
