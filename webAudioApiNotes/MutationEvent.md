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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/MutationEvent" class="breadcrumb-current-page"><span data-property="name">MutationEvent</span></a>

Table of contents
-----------------

Table of contents

-   [Preface](#preface)
-   [Mutation events list](#mutation_events_list)
-   [Usage](#usage)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

MutationEvent
=============

#### Deprecated

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

#### Note

<a href="https://www.w3.org/TR/DOM-Level-3-Events/#events-mutationevents" class="external">Mutation Events</a> (W3C DOM Level 3 Events) have been deprecated in favor of [Mutation Observers](https://developer.mozilla.org/en-US/docs/Web/API/MutationObserver) (W3C DOM4).

The `MutationEvent` interface provides event properties that are specific to modifications to the Document Object Model (DOM) hierarchy and nodes.

[Preface](#preface "Permalink to Preface")
------------------------------------------

The mutation events have been marked as deprecated in <a href="https://www.w3.org/TR/DOM-Level-3-Events/#events-mutationevents" class="external">the DOM Events specification</a>, as the API's design is flawed (see details in the "DOM Mutation Events Replacement: The Story So Far / Existing Points of Consensus" post to <a href="https://lists.w3.org/Archives/Public/public-webapps/2011JulSep/0779.html" class="external">public-webapps</a>).

[Mutation Observers](https://developer.mozilla.org/en-US/docs/Web/API/MutationObserver) have replaced mutation events in DOM4. They have been supported in [most popular browsers for some years](https://developer.mozilla.org/en-US/docs/Web/API/MutationObserver#browser_compatibility).

In addition, mutation events should be avoided because they have **performance issues** and **poor cross-browser support** (as described in the following sections).

### [Performance](#performance "Permalink to Performance")

Adding DOM mutation listeners to a document <a href="https://groups.google.com/group/mozilla.dev.platform/browse_thread/thread/2f42f1d75bb906fb?pli=1" class="external">profoundly degrades the performance</a> of further DOM modifications to that document (making them 1.5 - 7 times slower!). Moreover, removing the listeners does not reverse the damage.

The performance effect is <a href="https://groups.google.com/forum/#!topic/mozilla.dev.platform/UH2VqFQRTDA" class="link-https external">limited to the documents that have the mutation event listeners</a>.

### [Cross-browser support](#cross-browser_support "Permalink to Cross-browser support")

These events are not implemented consistently across different browsers, for example:

-   IE prior to version 9 didn't support the mutation events at all and does not implement some of them correctly in version 9 (<a href="http://help.dottoro.com/ljmcxjla.php" class="external">for example, DOMNodeInserted</a>)
-   WebKit doesn't support DOMAttrModified (see <a href="https://bugs.webkit.org/show_bug.cgi?id=8191" class="link-https external">webkit bug 8191</a> and <a href="https://engineering.silk.co/post/31921750832/mutation-events-what-happens" class="external">the workaround</a>)
-   "mutation name events", i.e. DOMElementNameChanged and DOMAttributeNameChanged are not supported in Firefox (as of version 11), and probably in other browsers as well.
-   ...

Dottoro <a href="http://help.dottoro.com/ljfvvdnm.php#additionalEvents" class="external">documents browser support for mutation events</a>.

[Mutation events list](#mutation_events_list "Permalink to Mutation events list")
---------------------------------------------------------------------------------

The following is a list of all mutation events, as defined in <a href="https://www.w3.org/TR/DOM-Level-3-Events/#events-mutationevents" class="external">DOM Level 3 Events specification</a>:

-   `DOMAttrModified`
-   `DOMAttributeNameChanged`
-   `DOMCharacterDataModified`
-   `DOMElementNameChanged`
-   `DOMNodeInserted`
-   `DOMNodeInsertedIntoDocument`
-   `DOMNodeRemoved`
-   `DOMNodeRemovedFromDocument`
-   `DOMSubtreeModified`

[Usage](#usage "Permalink to Usage")
------------------------------------

You can register a listener for mutation events using [`EventTarget.addEventListener()`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener) as follows:

    element.addEventListener("DOMNodeInserted", function (event) {
      // ...
    }, false);

The event object is passed to the listener in a `MutationEvent` (see <a href="https://www.w3.org/TR/DOM-Level-3-Events/#events-MutationEvent" class="external">its definition in the specification</a>) for most events, and <span class="page-not-created">`MutationNameEvent`</span> for `DOMAttributeNameChanged` and `DOMElementNameChanged`.

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

No compatibility data found for `api.MutationEvent`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   <span class="page-not-created">`MutationNameEvent`</span>

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/mutationevent/index.html "Folder: en-us/web/api/mutationevent (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FMutationEvent%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fmutationevent%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FMutationEvent%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fmutationevent%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F5737ba49f3f0c3fc7587d329f1362a7a66afdd80%0A*+Document+last+modified%3A+2021-05-31T16%3A58%3A42.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22MutationEvent%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/MutationEvent/contributors.txt)

#### Related Topics

1.  **[`MutationEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MutationEvent)**
2.  Inheritance:
    1.  [`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event)
3.  Related pages for DOM Events
    1.  [`CompositionEvent`](https://developer.mozilla.org/en-US/docs/Web/API/CompositionEvent)
    2.  [`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event)
    3.  [`EventListener`](https://developer.mozilla.org/en-US/docs/Web/API/EventListener)
    4.  [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)
    5.  [`FocusEvent`](https://developer.mozilla.org/en-US/docs/Web/API/FocusEvent)
    6.  [`InputEvent`](https://developer.mozilla.org/en-US/docs/Web/API/InputEvent)
    7.  [`KeyboardEvent`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent)
    8.  [`MouseEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent)
    9.  [`MouseScrollEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MouseScrollEvent)
    10. [`MouseWheelEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MouseWheelEvent)
    11. [`ProgressEvent`](https://developer.mozilla.org/en-US/docs/Web/API/ProgressEvent)
    12. [`UIEvent`](https://developer.mozilla.org/en-US/docs/Web/API/UIEvent)
    13. [`WheelEvent`](https://developer.mozilla.org/en-US/docs/Web/API/WheelEvent)

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
