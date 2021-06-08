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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/AbstractWorker" class="breadcrumb-current-page"><span data-property="name">AbstractWorker</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Properties](#properties)
-   [Methods](#methods)
-   [Example](#example)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

AbstractWorker
==============

<span class="seoSummary">The **`AbstractWorker`** interface of the [Web Workers API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API) is an abstract interface that defines properties and methods that are common to all types of worker, including not only the basic [`Worker`](https://developer.mozilla.org/en-US/docs/Web/API/Worker), but also [`ServiceWorker`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorker) and [`SharedWorker`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorker).</span> As an abstract class, you don't directly interact with `AbstractWorker`.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

*The `AbstractWorker` interface doesn't inherit any properties.*

### [Event handlers](#event_handlers "Permalink to Event handlers")

 [`AbstractWorker.onerror`](https://developer.mozilla.org/en-US/docs/Web/API/AbstractWorker/onerror)   
An [`EventListener`](https://developer.mozilla.org/en-US/docs/Web/API/EventListener) which is invoked whenever an [`ErrorEvent`](https://developer.mozilla.org/en-US/docs/Web/API/ErrorEvent) of type `error` event occurs.

[Methods](#methods "Permalink to Methods")
------------------------------------------

*The `AbstractWorker` interface doesn't implement or inherit any methods.*

[Example](#example "Permalink to Example")
------------------------------------------

As an abstract interface, you won't directly use `AbstractWorker` in your code. Instead, you'll interact with either [`Worker`](https://developer.mozilla.org/en-US/docs/Web/API/Worker) or [`SharedWorker`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorker), both of which inherit the properties of `AbstractWorker`.

This code snippet demonstrates the creation of a new `Worker` using the [`Worker()`](https://developer.mozilla.org/en-US/docs/Web/API/Worker/Worker "Worker()") constructor; it also shows how to then send a message to the worker.

    var myWorker = new Worker('worker.js');

    first.onchange = function() {
      myWorker.postMessage([first.value, second.value]);
      console.log('Message posted to worker');
    }

The worker's code is loaded from the file `"worker.js"`. This code assumes that there's an [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element represented by `first`; an event handler for the `change` event is established so that when the user changes the value of `first`, a message is posted to the worker to let it know.

You can find more examples on the MDN Web Docs GitHub repository:

-   <a href="https://github.com/mdn/simple-web-worker" class="external external-icon">Basic dedicated worker example</a> (<a href="https://mdn.github.io/simple-web-worker/" class="external external-icon">run dedicated worker</a>).
-   <a href="https://github.com/mdn/simple-shared-worker" class="external external-icon">Basic shared worker example</a> (<a href="https://mdn.github.io/simple-shared-worker/" class="external external-icon">run shared worker</a>).

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#abstractworker" class="external">HTML Living Standard<br />
<span class="small">The definition of 'AbstractWorker' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="about:unknown" class="external" title="The &#39;Unknown&#39; specification">Unknown</a>.</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   The [`Worker`](https://developer.mozilla.org/en-US/docs/Web/API/Worker), [`ServiceWorker`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorker), and [`SharedWorker`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorker) interfaces, which are all based upon `AbstractWorker`.
-   [Web Workers API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API)
-   [Using Web Workers](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Using_web_workers)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/abstractworker/index.html "Folder: en-us/web/api/abstractworker (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAbstractWorker%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fabstractworker%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAbstractWorker%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fabstractworker%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F67eb075e2a8ab4f59f4e00496c5b89d7d8fcef16%0A*+Document+last+modified%3A+2021-06-04T09%3A24%3A31.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22AbstractWorker%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Jun 4, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/AbstractWorker/contributors.txt)

Change your language Select your preferred language English (US) Español Français 日本語 한국어 Português (do Brasil) Русский 中文 (简体)

Change language

#### Related Topics

1.  **[Web Workers API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API)**
2.  **[`AbstractWorker`](https://developer.mozilla.org/en-US/docs/Web/API/AbstractWorker)**
3.  Properties
    1.  [`onerror`](https://developer.mozilla.org/en-US/docs/Web/API/AbstractWorker/onerror)
4.  Implemented by:
    1.  [`ServiceWorker`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorker)
    2.  [`SharedWorker`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorker)
    3.  [`Worker`](https://developer.mozilla.org/en-US/docs/Web/API/Worker)
5.  Related pages for Web Workers API
    1.  [`ChromeWorker`](https://developer.mozilla.org/en-US/docs/Web/API/ChromeWorker)
    2.  [`DedicatedWorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/DedicatedWorkerGlobalScope)
    3.  [`ServiceWorker`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorker)
    4.  [`SharedWorker`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorker)
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
