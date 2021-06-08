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
4.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/Worker/postMessage" class="breadcrumb-current-page"><span data-property="name">Worker.prototype.postMessage()</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Syntax](#syntax)
-   [Example](#example)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

Worker.prototype.postMessage()
==============================

The `postMessage()` method of the [`Worker`](https://developer.mozilla.org/en-US/docs/Web/API/Worker) interface sends a message to the worker's inner scope. This accepts a single parameter, which is the data to send to the worker. The data may be any value or JavaScript object handled by the [structured clone](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Structured_clone_algorithm) algorithm, which includes cyclical references.

Note this method blocks the thread which receives the message.

The `Worker` can send back information to the thread that spawned it using the [`DedicatedWorkerGlobalScope.postMessage`](https://developer.mozilla.org/en-US/docs/Web/API/DedicatedWorkerGlobalScope/postMessage) method.

[Syntax](#syntax "Permalink to Syntax")
---------------------------------------

    worker.postMessage(message, [transfer]);

### [Parameters](#parameters "Permalink to Parameters")

*message*  
The object to deliver to the worker; this will be in the `data` field in the event delivered to the [`DedicatedWorkerGlobalScope.onmessage`](https://developer.mozilla.org/en-US/docs/Web/API/DedicatedWorkerGlobalScope/onmessage) handler. This may be any value or JavaScript object handled by the [structured clone](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Structured_clone_algorithm) algorithm, which includes cyclical references.

If the `message` parameter is *not* provided, a `TypeError` will be thrown. If the data to be passed to the worker is unimportant, `null` or `undefined` can be passed explicitly.

*transfer* <span class="badge inline optional">Optional</span>  
An optional [array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of [`Transferable`](https://developer.mozilla.org/en-US/docs/Web/API/Transferable) objects to transfer ownership of. If the ownership of an object is transferred, it becomes unusable in the context it was sent from and becomes available only to the worker it was sent to.

Transferable objects are instances of classes like [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer), [`MessagePort`](https://developer.mozilla.org/en-US/docs/Web/API/MessagePort) or [`ImageBitmap`](https://developer.mozilla.org/en-US/docs/Web/API/ImageBitmap) objects that can be transferred. `null` is not an acceptable value for `transfer`.

### [Returns](#returns "Permalink to Returns")

Void.

[Example](#example "Permalink to Example")
------------------------------------------

The following code snippet shows the creation of a [`Worker`](https://developer.mozilla.org/en-US/docs/Web/API/Worker) object using the [`Worker()`](https://developer.mozilla.org/en-US/docs/Web/API/Worker/Worker "Worker()") constructor. When either of two form inputs (`first` and `second`) have their values changed, `change` events invoke `postMessage()` to send the value of both inputs to the current worker.

    var myWorker = new Worker('worker.js');

    first.onchange = function() {
      myWorker.postMessage([first.value,second.value]);
      console.log('Message posted to worker');
    }

    second.onchange = function() {
      myWorker.postMessage([first.value,second.value]);
      console.log('Message posted to worker');
    }

For a full example, see our <a href="https://github.com/mdn/simple-web-worker" class="external external-icon">simple worker example</a> (<a href="https://mdn.github.io/simple-web-worker/" class="external external-icon">run example</a>).

**Note**: `postMessage()` can only send a single object at once. As seen above, if you want to pass multiple values you can send an array.

### [Transfer Example](#transfer_example "Permalink to Transfer Example")

This example shows a Firefox add-on that transfers an `ArrayBuffer` from the main thread to the `ChromeWorker`, and then the `ChromeWorker` transfers it back to the main thread.

#### Main thread code:

    var myWorker = new ChromeWorker(self.path + 'myWorker.js');

    function handleMessageFromWorker(msg) {
        console.log('incoming message from worker, msg:', msg);
        switch (msg.data.aTopic) {
            case 'do_sendMainArrBuff':
                sendMainArrBuff(msg.data.aBuf)
                break;
            default:
                throw 'no aTopic on incoming message to ChromeWorker';
        }
    }

    myWorker.addEventListener('message', handleMessageFromWorker);

    // Ok lets create the buffer and send it
    var arrBuf = new ArrayBuffer(8);
    console.info('arrBuf.byteLength pre transfer:', arrBuf.byteLength);

    myWorker.postMessage(
        {
            aTopic: 'do_sendWorkerArrBuff',
            aBuf: arrBuf // The array buffer that we passed to the transferrable section 3 lines below
        },
        [
            arrBuf // The array buffer we created 9 lines above
        ]
    );

    console.info('arrBuf.byteLength post transfer:', arrBuf.byteLength);

#### Worker code

    self.onmessage = function (msg) {
        switch (msg.data.aTopic) {
            case 'do_sendWorkerArrBuff':
                    sendWorkerArrBuff(msg.data.aBuf)
                break;
            default:
                throw 'no aTopic on incoming message to ChromeWorker';
        }
    }

    function sendWorkerArrBuff(aBuf) {
        console.info('from worker, PRE send back aBuf.byteLength:', aBuf.byteLength);

        self.postMessage({aTopic:'do_sendMainArrBuff', aBuf:aBuf}, [aBuf]);

        console.info('from worker, POST send back aBuf.byteLength:', aBuf.byteLength);
    }

#### Output logged

    arrBuf.byteLength pre transfer: 8                              bootstrap.js:40
    arrBuf.byteLength post transfer: 0                             bootstrap.js:42

    from worker, PRE send back aBuf.byteLength: 8                  myWorker.js:5:2

    incoming message from worker, msg: message { ... }             bootstrap.js:20
    got back buf in main thread, aBuf.byteLength: 8                bootstrap.js:12

    from worker, POST send back aBuf.byteLength: 0                 myWorker.js:7:2

`byteLength` goes to 0 as it is transferred. To see a full working example of this Firefox demo add-on see here: <a href="https://github.com/Noitidart/ChromeWorker/tree/aca57d9cadc4e68af16201bdecbfb6f9a6f9ca6b" class="external">GitHub :: ChromeWorker - demo-transfer-arraybuffer</a>

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-worker-postmessage" class="external">HTML Living Standard<br />
<span class="small">The definition of 'Worker.postMessage()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   The [`Worker`](https://developer.mozilla.org/en-US/docs/Web/API/Worker) interface it belongs to.

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/worker/postmessage/index.html "Folder: en-us/web/api/worker/postmessage (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWorker%2FpostMessage%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fworker%2Fpostmessage%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWorker%2FpostMessage%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fworker%2Fpostmessage%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F94c536f9b3a50303a85e7963a4ff4958d1aec382%0A*+Document+last+modified%3A+2021-05-31T17%3A13%3A02.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22Worker.prototype.postMessage%28%29%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/Worker/postMessage/contributors.txt)

Change your languageSelect your preferred language English (US)EspañolFrançais한국어Русский中文 (简体)

Change language

#### Related Topics

1.  **[Web Workers API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API)**
2.  **[`Worker`](https://developer.mozilla.org/en-US/docs/Web/API/Worker)**
3.  Constructor
    1.  [`Worker()`](https://developer.mozilla.org/en-US/docs/Web/API/Worker/Worker)
4.  Properties
    1.  [`onerror`](https://developer.mozilla.org/en-US/docs/Web/API/AbstractWorker/onerror)
    2.  [`onmessage`](https://developer.mozilla.org/en-US/docs/Web/API/Worker/onmessage)
    3.  [`onmessageerror`](https://developer.mozilla.org/en-US/docs/Web/API/Worker/onmessageerror)
5.  Methods
    1.  *`postMessage()`*
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
