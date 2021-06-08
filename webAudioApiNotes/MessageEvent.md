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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/MessageEvent" class="breadcrumb-current-page"><span data-property="name">MessageEvent</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Constructor](#constructor)
-   [Properties](#properties)
-   [Methods](#methods)
-   [Examples](#examples)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

MessageEvent
============

The `MessageEvent` interface represents a message received by a target object.

This is used to represent messages in:

-   [Server-sent events](https://developer.mozilla.org/en-US/docs/Web/API/Server-sent_events) (see [`EventSource.onmessage`](https://developer.mozilla.org/en-US/docs/Web/API/EventSource/onmessage)).
-   [Web sockets](https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API) (see the `onmessage` property of the [WebSocket](https://developer.mozilla.org/en-US/docs/Web/API/WebSocket) interface).
-   Cross-document messaging (see [`Window.postMessage()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/postMessage) and <span class="page-not-created">`Window.onmessage`</span>).
-   [Channel messaging](https://developer.mozilla.org/en-US/docs/Web/API/Channel_Messaging_API) (see [`MessagePort.postMessage()`](https://developer.mozilla.org/en-US/docs/Web/API/MessagePort/postMessage) and [`MessagePort.onmessage`](https://developer.mozilla.org/en-US/docs/Web/API/MessagePort/onmessage)).
-   Cross-worker/document messaging (see the above two entries, but also [`Worker.postMessage()`](https://developer.mozilla.org/en-US/docs/Web/API/Worker/postMessage), [`Worker.onmessage`](https://developer.mozilla.org/en-US/docs/Web/API/Worker/onmessage), [`ServiceWorkerGlobalScope.onmessage`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/onmessage), etc.)
-   [Broadcast channels](https://developer.mozilla.org/en-US/docs/Web/API/Broadcast_Channel_API) (see [`Broadcastchannel.postMessage()`](https://developer.mozilla.org/en-US/docs/Web/API/BroadcastChannel/postMessage)) and [`BroadcastChannel.onmessage`](https://developer.mozilla.org/en-US/docs/Web/API/BroadcastChannel/onmessage)).
-   WebRTC data channels (see [`RTCDataChannel.onmessage`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/onmessage)).

The action triggered by this event is defined in a function set as the event handler for the relevant `message` event (e.g. using an `onmessage` handler as listed above).

**Note:** This feature is available in [Web Workers](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API)

  

[Constructor](#constructor "Permalink to Constructor")
------------------------------------------------------

[`MessageEvent()`](https://developer.mozilla.org/en-US/docs/Web/API/MessageEvent/MessageEvent "MessageEvent()")  
Creates a new `MessageEvent`.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

*This interface also inherits properties from its parent, [`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event).*

[`MessageEvent.data`](https://developer.mozilla.org/en-US/docs/Web/API/MessageEvent/data) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
The data sent by the message emitter.

[`MessageEvent.origin`](https://developer.mozilla.org/en-US/docs/Web/API/MessageEvent/origin) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
A [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString) representing the origin of the message emitter.

[`MessageEvent.lastEventId`](https://developer.mozilla.org/en-US/docs/Web/API/MessageEvent/lastEventId) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) representing a unique ID for the event.

[`MessageEvent.source`](https://developer.mozilla.org/en-US/docs/Web/API/MessageEvent/source) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
A `MessageEventSource` (which can be a <span class="page-not-created">`WindowProxy`</span>, [`MessagePort`](https://developer.mozilla.org/en-US/docs/Web/API/MessagePort), or [`ServiceWorker`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorker) object) representing the message emitter.

[`MessageEvent.ports`](https://developer.mozilla.org/en-US/docs/Web/API/MessageEvent/ports) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
An array of [`MessagePort`](https://developer.mozilla.org/en-US/docs/Web/API/MessagePort) objects representing the ports associated with the channel the message is being sent through (where appropriate, e.g. in channel messaging or when sending a message to a shared worker).

[Methods](#methods "Permalink to Methods")
------------------------------------------

*This interface also inherits methods from its parent, [`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event).*

<span class="page-not-created">`initMessageEvent()`</span>   
Initializes a message event. **Do not use this anymore** — **use the [`MessageEvent()`](https://developer.mozilla.org/en-US/docs/Web/API/MessageEvent/MessageEvent "MessageEvent()") constructor instead.**

[Examples](#examples "Permalink to Examples")
---------------------------------------------

In our <a href="https://github.com/mdn/simple-shared-worker" class="external external-icon">Basic shared worker example</a> (<a href="https://mdn.github.io/simple-shared-worker/" class="external external-icon">run shared worker</a>), we have two HTML pages, each of which uses some JavaScript to perform a simple calculation. The different scripts are using the same worker file to perform the calculation — they can both access it, even if their pages are running inside different windows.

The following code snippet shows creation of a [`SharedWorker`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorker) object using the [`SharedWorker()`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorker/SharedWorker "SharedWorker()") constructor. Both scripts contain this:

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#messageevent" class="external">HTML Living Standard<br />
<span class="small">The definition of 'MessageEvent' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [`ExtendableMessageEvent`](https://developer.mozilla.org/en-US/docs/Web/API/ExtendableMessageEvent) — similar to this interface but used in interfaces that needs to give more flexibility to authors.

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/messageevent/index.html "Folder: en-us/web/api/messageevent (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FMessageEvent%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fmessageevent%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FMessageEvent%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fmessageevent%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F5737ba49f3f0c3fc7587d329f1362a7a66afdd80%0A*+Document+last+modified%3A+2021-05-31T16%3A58%3A42.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22MessageEvent%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/MessageEvent/contributors.txt)

Change your languageSelect your preferred language English (US)DeutschEspañolFrançais日本語한국어中文 (简体)正體中文 (繁體)

Change language

#### Related Topics

1.  **[`MessageEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MessageEvent)**
2.  Constructor
    1.  [`MessageEvent()`](https://developer.mozilla.org/en-US/docs/Web/API/MessageEvent/MessageEvent)
3.  Properties
    1.  [`data`](https://developer.mozilla.org/en-US/docs/Web/API/MessageEvent/data)
    2.  [`lastEventId`](https://developer.mozilla.org/en-US/docs/Web/API/MessageEvent/lastEventId)
    3.  [`origin`](https://developer.mozilla.org/en-US/docs/Web/API/MessageEvent/origin)
    4.  [`ports`](https://developer.mozilla.org/en-US/docs/Web/API/MessageEvent/ports)
    5.  [`source`](https://developer.mozilla.org/en-US/docs/Web/API/MessageEvent/source)
4.  Inheritance:
    1.  [`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event)
5.  Related pages for HTML DOM
    1.  [`BeforeUnloadEvent`](https://developer.mozilla.org/en-US/docs/Web/API/BeforeUnloadEvent)
    2.  [`DOMStringMap`](https://developer.mozilla.org/en-US/docs/Web/API/DOMStringMap)
    3.  [`ErrorEvent`](https://developer.mozilla.org/en-US/docs/Web/API/ErrorEvent)
    4.  [`GlobalEventHandlers`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers)
    5.  [`HTMLAnchorElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAnchorElement)
    6.  [`HTMLAreaElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement)
    7.  [`HTMLAudioElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAudioElement)
    8.  [`HTMLBRElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLBRElement)
    9.  [`HTMLBaseElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLBaseElement)
    10. [`HTMLBaseFontElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLBaseFontElement)
    11. [`HTMLBodyElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLBodyElement)
    12. [`HTMLButtonElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLButtonElement)
    13. [`HTMLCanvasElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement)
    14. [`HTMLContentElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLContentElement)
    15. [`HTMLDListElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDListElement)
    16. [`HTMLDataElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDataElement)
    17. [`HTMLDataListElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDataListElement)
    18. [`HTMLDialogElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDialogElement)
    19. [`HTMLDivElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDivElement)
    20. [`HTMLDocument`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDocument)
    21. [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
    22. [`HTMLEmbedElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLEmbedElement)
    23. [`HTMLFieldSetElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFieldSetElement)
    24. [`HTMLFormControlsCollection`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormControlsCollection)
    25. [`HTMLFormElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement)
    26. [`HTMLFrameSetElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFrameSetElement)
    27. [`HTMLHRElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLHRElement)
    28. [`HTMLHeadElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLHeadElement)
    29. [`HTMLHeadingElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLHeadingElement)
    30. [`HTMLHtmlElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLHtmlElement)
    31. [`HTMLIFrameElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLIFrameElement)
    32. [`HTMLImageElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement)
    33. [`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement)
    34. [`HTMLIsIndexElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLIsIndexElement)
    35. [`HTMLKeygenElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLKeygenElement)
    36. [`HTMLLIElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLLIElement)
    37. [`HTMLLabelElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLLabelElement)
    38. [`HTMLLegendElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLLegendElement)
    39. [`HTMLLinkElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLLinkElement)
    40. [`HTMLMapElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMapElement)
    41. [`HTMLMediaElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement)
    42. [`HTMLMetaElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMetaElement)
    43. [`HTMLMeterElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMeterElement)
    44. [`HTMLModElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLModElement)
    45. [`HTMLOListElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOListElement)
    46. [`HTMLObjectElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLObjectElement)
    47. [`HTMLOptGroupElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOptGroupElement)
    48. [`HTMLOptionElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOptionElement)
    49. [`HTMLOptionsCollection`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOptionsCollection)
    50. [`HTMLOutputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOutputElement)
    51. [`HTMLParagraphElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLParagraphElement)
    52. [`HTMLParamElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLParamElement)
    53. [`HTMLPictureElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLPictureElement)
    54. [`HTMLPreElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLPreElement)
    55. [`HTMLProgressElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLProgressElement)
    56. [`HTMLQuoteElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLQuoteElement)
    57. [`HTMLScriptElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLScriptElement)
    58. [`HTMLSelectElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement)
    59. [`HTMLShadowElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLShadowElement)
    60. [`HTMLSourceElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSourceElement)
    61. [`HTMLSpanElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSpanElement)
    62. [`HTMLStyleElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLStyleElement)
    63. [`HTMLTableCaptionElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableCaptionElement)
    64. [`HTMLTableCellElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableCellElement)
    65. [`HTMLTableColElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableColElement)
    66. [`HTMLTableDataCellElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableDataCellElement)
    67. [`HTMLTableElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableElement)
    68. [`HTMLTableHeaderCellElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableHeaderCellElement)
    69. [`HTMLTableRowElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableRowElement)
    70. [`HTMLTableSectionElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableSectionElement)
    71. [`HTMLTemplateElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTemplateElement)
    72. [`HTMLTextAreaElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTextAreaElement)
    73. [`HTMLTimeElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTimeElement)
    74. [`HTMLTitleElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTitleElement)
    75. [`HTMLTrackElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTrackElement)
    76. [`HTMLUListElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLUListElement)
    77. [`HTMLUnknownElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLUnknownElement)
    78. [`HTMLVideoElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLVideoElement)
    79. [`HashChangeEvent`](https://developer.mozilla.org/en-US/docs/Web/API/HashChangeEvent)
    80. [`History`](https://developer.mozilla.org/en-US/docs/Web/API/History)
    81. [`ImageData`](https://developer.mozilla.org/en-US/docs/Web/API/ImageData)
    82. [`Location`](https://developer.mozilla.org/en-US/docs/Web/API/Location)
    83. [`MessageChannel`](https://developer.mozilla.org/en-US/docs/Web/API/MessageChannel)
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

#### Mozilla

-   <a href="https://twitter.com/mozilla" class="social-icon twitter"><span class="visually-hidden">Mozilla on Twitter</span></a>
-   <a href="https://www.instagram.com/mozillagram/" class="social-icon instagram"><span class="visually-hidden">Mozilla on Instagram</span></a>

© 2005-2021 Mozilla and individual contributors. Content is available under [these licenses](https://developer.mozilla.org/docs/MDN/About#Copyrights_and_licenses).

-   [Terms](https://www.mozilla.org/about/legal/terms/mozilla)
-   [Privacy](https://www.mozilla.org/privacy/websites/)
-   [Cookies](https://www.mozilla.org/privacy/websites/#cookies)
