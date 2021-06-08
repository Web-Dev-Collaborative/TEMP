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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/History" class="breadcrumb-current-page"><span data-property="name">History</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Properties](#properties)
-   [Methods](#methods)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

History
=======

The **`History`** interface allows manipulation of the browser *session history*, that is the pages visited in the tab or frame that the current page is loaded in.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

*The `History` interface doesn't inherit any property.*

[`length`](https://developer.mozilla.org/en-US/docs/Web/API/History/length "length") <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns an `Integer` representing the number of elements in the session history, including the currently loaded page. For example, for a page loaded in a new tab this property returns `1`.

[`scrollRestoration`](https://developer.mozilla.org/en-US/docs/Web/API/History/scrollRestoration "scrollRestoration")  
Allows web applications to explicitly set default scroll restoration behavior on history navigation. This property can be either `auto` or `manual`.

[`state`](https://developer.mozilla.org/en-US/docs/Web/API/History/state "state") <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns an `any` value representing the state at the top of the history stack. This is a way to look at the state without having to wait for a `popstate` event.

[Methods](#methods "Permalink to Methods")
------------------------------------------

*The `History`* *interface doesn't inherit any methods.*

[`back()`](https://developer.mozilla.org/en-US/docs/Web/API/History/back "back()")  
This asynchronous method goes to the previous page in session history, the same action as when the user clicks the browser's Back button. Equivalent to `history.go(-1)`.

Calling this method to go back beyond the first page in the session history has no effect and doesn't raise an exception.

[`forward()`](https://developer.mozilla.org/en-US/docs/Web/API/History/forward "forward()")  
This asynchronous method goes to the next page in session history, the same action as when the user clicks the browser's Forward button; this is equivalent to `history.go(1)`.

Calling this method to go forward beyond the most recent page in the session history has no effect and doesn't raise an exception.

[`go()`](https://developer.mozilla.org/en-US/docs/Web/API/History/go "go()")  
Asynchronously loads a page from the session history, identified by its relative location to the current page, for example `-1` for the previous page or `1` for the next page. If you specify an out-of-bounds value (for instance, specifying `-1` when there are no previously-visited pages in the session history), this method silently has no effect. Calling `go()` without parameters or a value of `0` reloads the current page. Internet Explorer lets you specify a string, instead of an integer, to go to a specific URL in the history list.

[`pushState()`](https://developer.mozilla.org/en-US/docs/Web/API/History/pushState "pushState()")  
Pushes the given data onto the session history stack with the specified title (and, if provided, URL). The data is treated as opaque by the DOM; you may specify any JavaScript object that can be serialized.  Note that all browsers but Safari currently ignore the *title* parameter. For more information, see [Working with the History API](https://developer.mozilla.org/en-US/docs/Web/API/History_API/Working_with_the_History_API).

[`replaceState()`](https://developer.mozilla.org/en-US/docs/Web/API/History/replaceState "replaceState()")  
Updates the most recent entry on the history stack to have the specified data, title, and, if provided, URL. The data is treated as opaque by the DOM; you may specify any JavaScript object that can be serialized.  Note that all browsers but Safari currently ignore the *title* parameter. For more information, see [Working with the History API](https://developer.mozilla.org/en-US/docs/Web/API/History_API/Working_with_the_History_API).

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/browsers.html#the-history-interface" class="external">HTML Living Standard<br />
<span class="small">The definition of 'History' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Adds the <code>scrollRestoration</code> attribute.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/browsers.html#the-history-interface" class="external">HTML5<br />
<span class="small">The definition of 'History' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   The [`Window.history`](https://developer.mozilla.org/en-US/docs/Web/API/Window/history) property returning the history of the current session.

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/history/index.html "Folder: en-us/web/api/history (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FHistory%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fhistory%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FHistory%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fhistory%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fcb20a8045f6cbdbd224b1068e46c8644470dd8c3%0A*+Document+last+modified%3A+2021-06-01T09%3A10%3A31.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22History%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Jun 1, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/History/contributors.txt)

Change your languageSelect your preferred language English (US)EspañolFrançais日本語한국어Português (do Brasil)Русский中文 (简体)正體中文 (繁體)

Change language

#### Related Topics

1.  **[History API](https://developer.mozilla.org/en-US/docs/Web/API/History_API)**
2.  **[`History`](https://developer.mozilla.org/en-US/docs/Web/API/History)**
3.  Properties
    1.  [`length`](https://developer.mozilla.org/en-US/docs/Web/API/History/length)
    2.  [`scrollRestoration`](https://developer.mozilla.org/en-US/docs/Web/API/History/scrollRestoration)
    3.  [`state`](https://developer.mozilla.org/en-US/docs/Web/API/History/state)
4.  Methods
    1.  [`back()`](https://developer.mozilla.org/en-US/docs/Web/API/History/back)
    2.  [`forward()`](https://developer.mozilla.org/en-US/docs/Web/API/History/forward)
    3.  [`go()`](https://developer.mozilla.org/en-US/docs/Web/API/History/go)
    4.  [`pushState()`](https://developer.mozilla.org/en-US/docs/Web/API/History/pushState)
    5.  [`replaceState()`](https://developer.mozilla.org/en-US/docs/Web/API/History/replaceState)

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
