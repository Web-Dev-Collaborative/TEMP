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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/UIEvent" class="breadcrumb-current-page"><span data-property="name">UIEvent</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Constructors](#constructors)
-   [Properties](#properties)
-   [Methods](#methods)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

UIEvent
=======

The **`UIEvent`** interface represents simple user interface events.

`UIEvent` derives from [`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event). Although the [`UIEvent.initUIEvent()`](https://developer.mozilla.org/en-US/docs/Web/API/UIEvent/initUIEvent) method is kept for backward compatibility, you should create a `UIEvent` object using the [`UIEvent()`](https://developer.mozilla.org/en-US/docs/Web/API/UIEvent/UIEvent "UIEvent()") constructor.

Several interfaces are direct or indirect descendants of this one: [`MouseEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent), [`TouchEvent`](https://developer.mozilla.org/en-US/docs/Web/API/TouchEvent), [`FocusEvent`](https://developer.mozilla.org/en-US/docs/Web/API/FocusEvent), [`KeyboardEvent`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent), [`WheelEvent`](https://developer.mozilla.org/en-US/docs/Web/API/WheelEvent), [`InputEvent`](https://developer.mozilla.org/en-US/docs/Web/API/InputEvent), and [`CompositionEvent`](https://developer.mozilla.org/en-US/docs/Web/API/CompositionEvent).

[Constructors](#constructors "Permalink to Constructors")
---------------------------------------------------------

[`UIEvent()`](https://developer.mozilla.org/en-US/docs/Web/API/UIEvent/UIEvent "UIEvent()")  
Creates a `UIEvent` object.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

*This interface also inherits properties of its parent, [`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event).*

[`UIEvent.detail`](https://developer.mozilla.org/en-US/docs/Web/API/UIEvent/detail)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a `long` with details about the event, depending on the event type.

[`UIEvent.isChar`](https://developer.mozilla.org/en-US/docs/Web/API/UIEvent/isChar) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the event produced a key character or not.

[`UIEvent.layerX`](https://developer.mozilla.org/en-US/docs/Web/API/UIEvent/layerX) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the horizontal coordinate of the event relative to the current layer.

[`UIEvent.layerY`](https://developer.mozilla.org/en-US/docs/Web/API/UIEvent/layerY) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the vertical coordinate of the event relative to the current layer.

[`UIEvent.pageX`](https://developer.mozilla.org/en-US/docs/Web/API/UIEvent/pageX) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the horizontal coordinate of the event relative to the whole document.

[`UIEvent.pageY`](https://developer.mozilla.org/en-US/docs/Web/API/UIEvent/pageY) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the vertical coordinate of the event relative to the whole document.

[`UIEvent.sourceCapabilities`](https://developer.mozilla.org/en-US/docs/Web/API/UIEvent/sourceCapabilities) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns an instance of the `InputDeviceCapabilities` interface, which provides information about the physical device responsible for generating a touch event.

[`UIEvent.view`](https://developer.mozilla.org/en-US/docs/Web/API/UIEvent/view)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a <span class="page-not-created">`WindowProxy`</span> that contains the view that generated the event.

<span class="page-not-created">`UIEvent.which`</span> <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the numeric `keyCode` of the key pressed, or the character code (`charCode`) for an alphanumeric key pressed.

[Methods](#methods "Permalink to Methods")
------------------------------------------

*This interface also inherits methods of its parent, [`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event).*

[`UIEvent.initUIEvent()`](https://developer.mozilla.org/en-US/docs/Web/API/UIEvent/initUIEvent)   
Initializes a `UIEvent` object. If the event has already being dispatched, this method does nothing.

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/InputDeviceCapabilities/" class="external" title="The &#39;InputDeviceCapabilities&#39; specification">InputDeviceCapabilities</a></td><td><span class="spec-draft">Draft</span></td><td>Added <code>sourceCapabilities</code> property.</td></tr><tr class="even"><td><a href="https://w3c.github.io/uievents/" class="external" title="The &#39;UI Events&#39; specification">UI Events</a></td><td><span class="spec-wd">Working Draft</span></td><td>Extend DOM3</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#interface-UIEvent" class="external">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'UIEvent' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Added the <code>UIEvent()</code> constructor, deprecated the <code>initUIEvent()</code> method and changed the type of <code>view</code> from <code>AbstractView</code> to <code>WindowProxy</code>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Events/events.html#Events-UIEvent" class="external">Document Object Model (DOM) Level 2 Events Specification<br />
<span class="small">The definition of 'UIEvent' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Introduction to events](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events)
-   [`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/uievent/index.html "Folder: en-us/web/api/uievent (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FUIEvent%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fuievent%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FUIEvent%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fuievent%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F753712510ce0974a3fc1483a9e8820d85721d09a%0A*+Document+last+modified%3A+2021-05-31T16%3A29%3A13.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22UIEvent%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/UIEvent/contributors.txt)

Change your languageSelect your preferred language English (US)EspañolFrançais日本語中文 (简体)正體中文 (繁體)

Change language

#### Related Topics

1.  **[`UIEvent`](https://developer.mozilla.org/en-US/docs/Web/API/UIEvent)**
2.  Constructor
    1.  [`UIEvent()`](https://developer.mozilla.org/en-US/docs/Web/API/UIEvent/UIEvent)
3.  Properties
    1.  [`detail`](https://developer.mozilla.org/en-US/docs/Web/API/UIEvent/detail)
    2.  [`isChar`](https://developer.mozilla.org/en-US/docs/Web/API/UIEvent/isChar)
    3.  [`layerX`](https://developer.mozilla.org/en-US/docs/Web/API/UIEvent/layerX)
    4.  [`layerY`](https://developer.mozilla.org/en-US/docs/Web/API/UIEvent/layerY)
    5.  [`pageX`](https://developer.mozilla.org/en-US/docs/Web/API/UIEvent/pageX)
    6.  [`pageY`](https://developer.mozilla.org/en-US/docs/Web/API/UIEvent/pageY)
    7.  [`sourceCapabilities`](https://developer.mozilla.org/en-US/docs/Web/API/UIEvent/sourceCapabilities)
    8.  [`view`](https://developer.mozilla.org/en-US/docs/Web/API/UIEvent/view)
4.  Methods
    1.  [`initUIEvent`](https://developer.mozilla.org/en-US/docs/Web/API/UIEvent/initUIEvent)
5.  Events
    1.  [`initUIEvent`](https://developer.mozilla.org/en-US/docs/Web/API/UIEvent/initUIEvent)
6.  Inheritance:
    1.  [`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event)
7.  Related pages for DOM Events
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
    11. [`MutationEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MutationEvent)
    12. [`ProgressEvent`](https://developer.mozilla.org/en-US/docs/Web/API/ProgressEvent)
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
