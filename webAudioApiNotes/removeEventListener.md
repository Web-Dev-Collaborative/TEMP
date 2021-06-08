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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/EventTarget" class="breadcrumb-penultimate"><span data-property="name">EventTarget</span></a>
4.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/removeEventListener" class="breadcrumb-current-page"><span data-property="name">EventTarget.removeEventListener()</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Syntax](#syntax)
-   [Notes](#notes)
-   [Example](#example)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [Polyfill to support older browsers](#polyfill_to_support_older_browsers)
-   [See also](#see_also)

EventTarget.removeEventListener()
=================================

<span class="seoSummary">The **`EventTarget.removeEventListener()`** method removes from the [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget) an event listener previously registered with [`EventTarget.addEventListener()`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener). The event listener to be removed is identified using a combination of the event type, the event listener function itself, and various optional options that may affect the matching process; see [Matching event listeners for removal](#matching_event_listeners_for_removal)</span>

Note that event listeners can also be removed by passing an [`AbortSignal`](https://developer.mozilla.org/en-US/docs/Web/API/AbortSignal) to an [`addEventListener()`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener "addEventListener()") and then later calling [`abort()`](https://developer.mozilla.org/en-US/docs/Web/API/AbortController/abort "abort()") on the controller owning the signal.

[Syntax](#syntax "Permalink to Syntax")
---------------------------------------

    target.removeEventListener(type, listener[, options]);
    target.removeEventListener(type, listener[, useCapture]);

### [Parameters](#parameters "Permalink to Parameters")

`type`  
A string which specifies the type of event for which to remove an event listener.

`listener`  
The [`EventListener`](https://developer.mozilla.org/en-US/docs/Web/API/EventListener) function of the event handler to remove from the event target.

`options` <span class="badge inline optional">Optional</span>  
An options object that specifies characteristics about the event listener.

The available options are:

-   `capture`: A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) which indicates that events of this type will be dispatched to the registered `listener` before being dispatched to any [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget) beneath it in the DOM tree.
-    `mozSystemGroup`: A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) available only for code running in XBL or in Firefox's chrome which indicates if the listener will be added to the system group.

`useCapture` <span class="badge inline optional">Optional</span>  
Specifies whether the [`EventListener`](https://developer.mozilla.org/en-US/docs/Web/API/EventListener) to be removed is registered as a capturing listener or not. If this parameter is absent, a default value of `false` is assumed.

If a listener is registered twice, one with capture and one without, remove each one separately. Removal of a capturing listener does not affect a non-capturing version of the same listener, and vice versa.

### [Return value](#return_value "Permalink to Return value")

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined)

### [Matching event listeners for removal](#matching_event_listeners_for_removal "Permalink to Matching event listeners for removal")

Given an event listener previously added by calling [`addEventListener()`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener "addEventListener()"), you may eventually come to a point at which you need to remove it. Obviously, you need to specify the same `type` and `listener` parameters to `removeEventListener()`. But what about the `options` or `useCapture` parameters?

While `addEventListener()` will let you add the same listener more than once for the same type if the options are different, the only option `removeEventListener()` checks is the `capture`/`useCapture` flag. Its value must match for `removeEventListener()` to match, but the other values don't.

For example, consider this call to `addEventListener()`:

    element.addEventListener("mousedown", handleMouseDown, true);

Now consider each of these two calls to `removeEventListener()`:

    element.removeEventListener("mousedown", handleMouseDown, false);     // Fails
    element.removeEventListener("mousedown", handleMouseDown, true);      // Succeeds

The first call fails because the value of `useCapture` doesn't match. The second succeeds, since `useCapture` matches up.

Now consider this:

    element.addEventListener("mousedown", handleMouseDown, { passive: true });

Here, we specify an `options` object in which `passive` is set to `true`, while the other options are left to the default value of `false`.

Now look at each of these calls to `removeEventListener()` in turn. Any of them in which `capture` or `useCapture` is `true` fail; all others succeed.

Only the `capture` setting matters to `removeEventListener()`.

    element.removeEventListener("mousedown", handleMouseDown, { passive: true });     // Succeeds
    element.removeEventListener("mousedown", handleMouseDown, { capture: false });    // Succeeds
    element.removeEventListener("mousedown", handleMouseDown, { capture: true });     // Fails
    element.removeEventListener("mousedown", handleMouseDown, { passive: false });    // Succeeds
    element.removeEventListener("mousedown", handleMouseDown, false);                 // Succeeds
    element.removeEventListener("mousedown", handleMouseDown, true);                  // Fails

It's worth noting that some browser releases have been inconsistent on this, and unless you have specific reasons otherwise, it's probably wise to use the same values used for the call to `addEventListener()` when calling `removeEventListener()`.

[Notes](#notes "Permalink to Notes")
------------------------------------

If an [`EventListener`](https://developer.mozilla.org/en-US/docs/Web/API/EventListener) is removed from an [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget) while it is processing an event, it will not be triggered by the current actions. An [`EventListener`](https://developer.mozilla.org/en-US/docs/Web/API/EventListener) will not be invoked for the event it was registered for after being removed. However, it can be reattached.

Calling `removeEventListener()` with arguments that do not identify any currently registered [`EventListener`](https://developer.mozilla.org/en-US/docs/Web/API/EventListener) on the `EventTarget` has no effect.

[Example](#example "Permalink to Example")
------------------------------------------

This example shows how to add a `mouseover`-based event listener that removes a `click`-based event listener.

    const body = document.querySelector('body')
    const clickTarget = document.getElementById('click-target')
    const mouseOverTarget = document.getElementById('mouse-over-target')

    let toggle = false;
    function makeBackgroundYellow() {
        if (toggle) {
            body.style.backgroundColor = 'white';
        } else {
            body.style.backgroundColor = 'yellow';
        }

        toggle = !toggle;
    }

    clickTarget.addEventListener('click',
        makeBackgroundYellow,
        false
    );

    mouseOverTarget.addEventListener('mouseover', function () {
        clickTarget.removeEventListener('click',
            makeBackgroundYellow,
            false
        );
    });

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-eventtarget-removeeventlistener" class="external">DOM<br />
<span class="small">The definition of 'EventTarget.removeEventListener()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/dom/#dom-eventtarget-removeeventlistener" class="external">DOM4<br />
<span class="small">The definition of 'EventTarget.removeEventListener()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Events/events.html#Events-EventTarget-removeEventListener" class="external">Document Object Model (DOM) Level 2 Events Specification<br />
<span class="small">The definition of 'EventTarget.removeEventListener()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[Polyfill to support older browsers](#polyfill_to_support_older_browsers "Permalink to Polyfill to support older browsers")
---------------------------------------------------------------------------------------------------------------------------

`addEventListener()` and `removeEventListener()` are not present in older browsers. You can work around this by inserting the following code at the beginning of your scripts, allowing the use of `addEventListener()` and `removeEventListener()` in implementations that do not natively support it. However, this method will not work on Internet Explorer 7 or earlier, since extending the `Element.prototype` was not supported until Internet Explorer 8.

    if (!Element.prototype.addEventListener) {
      var oListeners = {};
      function runListeners(oEvent) {
        if (!oEvent) { oEvent = window.event; }
        for (var iLstId = 0, iElId = 0, oEvtListeners = oListeners[oEvent.type]; iElId < oEvtListeners.aEls.length; iElId++) {
          if (oEvtListeners.aEls[iElId] === this) {
            for (iLstId; iLstId < oEvtListeners.aEvts[iElId].length; iLstId++) { oEvtListeners.aEvts[iElId][iLstId].call(this, oEvent); }
            break;
          }
        }
      }
      Element.prototype.addEventListener = function (sEventType, fListener /*, useCapture (will be ignored!) */) {
        if (oListeners.hasOwnProperty(sEventType)) {
          var oEvtListeners = oListeners[sEventType];
          for (var nElIdx = -1, iElId = 0; iElId < oEvtListeners.aEls.length; iElId++) {
            if (oEvtListeners.aEls[iElId] === this) { nElIdx = iElId; break; }
          }
          if (nElIdx === -1) {
            oEvtListeners.aEls.push(this);
            oEvtListeners.aEvts.push([fListener]);
            this["on" + sEventType] = runListeners;
          } else {
            var aElListeners = oEvtListeners.aEvts[nElIdx];
            if (this["on" + sEventType] !== runListeners) {
              aElListeners.splice(0);
              this["on" + sEventType] = runListeners;
            }
            for (var iLstId = 0; iLstId < aElListeners.length; iLstId++) {
              if (aElListeners[iLstId] === fListener) { return; }
            }
            aElListeners.push(fListener);
          }
        } else {
          oListeners[sEventType] = { aEls: [this], aEvts: [ [fListener] ] };
          this["on" + sEventType] = runListeners;
        }
      };
      Element.prototype.removeEventListener = function (sEventType, fListener /*, useCapture (will be ignored!) */) {
        if (!oListeners.hasOwnProperty(sEventType)) { return; }
        var oEvtListeners = oListeners[sEventType];
        for (var nElIdx = -1, iElId = 0; iElId < oEvtListeners.aEls.length; iElId++) {
          if (oEvtListeners.aEls[iElId] === this) { nElIdx = iElId; break; }
        }
        if (nElIdx === -1) { return; }
        for (var iLstId = 0, aElListeners = oEvtListeners.aEvts[nElIdx]; iLstId < aElListeners.length; iLstId++) {
          if (aElListeners[iLstId] === fListener) { aElListeners.splice(iLstId, 1); }
        }
      };
    }

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [`EventTarget.addEventListener()`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/eventtarget/removeeventlistener/index.html "Folder: en-us/web/api/eventtarget/removeeventlistener (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FEventTarget%2FremoveEventListener%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Feventtarget%2Fremoveeventlistener%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FEventTarget%2FremoveEventListener%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Feventtarget%2Fremoveeventlistener%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F792c21d9b034abfd4082de517d7d02226c4770a6%0A*+Document+last+modified%3A+2021-06-02T18%3A04%3A41.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22EventTarget.removeEventListener%28%29%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Jun 2, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/removeEventListener/contributors.txt)

Change your languageSelect your preferred language English (US)EspañolFrançais日本語한국어Português (do Brasil)Русский中文 (简体)正體中文 (繁體)

Change language

#### Related Topics

1.  **[`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)**
2.  Constructor
    1.  [`EventTarget()`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/EventTarget)
3.  Methods
    1.  [`addEventListener()`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener)
    2.  [`dispatchEvent()`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/dispatchEvent)
    3.  *`removeEventListener()`*
4.  Related pages for DOM Events
    1.  [`CompositionEvent`](https://developer.mozilla.org/en-US/docs/Web/API/CompositionEvent)
    2.  [`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event)
    3.  [`EventListener`](https://developer.mozilla.org/en-US/docs/Web/API/EventListener)
    4.  [`FocusEvent`](https://developer.mozilla.org/en-US/docs/Web/API/FocusEvent)
    5.  [`InputEvent`](https://developer.mozilla.org/en-US/docs/Web/API/InputEvent)
    6.  [`KeyboardEvent`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent)
    7.  [`MouseEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent)
    8.  [`MouseScrollEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MouseScrollEvent)
    9.  [`MouseWheelEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MouseWheelEvent)
    10. [`MutationEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MutationEvent)
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
-   [Terms](https://www.mozilla.org/about/legal/terms/mozilla)
-   [Privacy](https://www.mozilla.org/privacy/websites/)
-   [Cookies](https://www.mozilla.org/privacy/websites/#cookies)
