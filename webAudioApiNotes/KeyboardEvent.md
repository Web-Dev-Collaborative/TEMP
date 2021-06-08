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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent" class="breadcrumb-current-page"><span data-property="name">KeyboardEvent</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Constructor](#constructor)
-   [Constants](#constants)
-   [Properties](#properties)
-   [Methods](#methods)
-   [Obsolete methods](#obsolete_methods)
-   [Obsolete properties](#obsolete_properties)
-   [Events](#events)
-   [Usage notes](#usage_notes)
-   [Example](#example)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

KeyboardEvent
=============

<span class="seoSummary">**`KeyboardEvent`** objects describe a user interaction with the keyboard; each event describes a single interaction between the user and a key (or combination of a key with modifier keys) on the keyboard.</span> The event type (`keydown`, `keypress`, or `keyup`) identifies what kind of keyboard activity occurred.

**Note:** `KeyboardEvent` events just indicate what interaction the user had with a key on the keyboard at a low level, providing no contextual meaning to that interaction. When you need to handle text input, use the `input` event instead. Keyboard events may not be fired if the user is using an alternate means of entering text, such as a handwriting system on a tablet or graphics tablet.

[Constructor](#constructor "Permalink to Constructor")
------------------------------------------------------

[`KeyboardEvent()`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/KeyboardEvent "KeyboardEvent()")  
Creates a new `KeyboardEvent` object.

[Constants](#constants "Permalink to Constants")
------------------------------------------------

The `KeyboardEvent` interface defines the following constants.

### [Keyboard locations](#keyboard_locations "Permalink to Keyboard locations")

The following constants identify which part of the keyboard the key event originates from. They are accessed as `KeyboardEvent.DOM_KEY_LOCATION_STANDARD` and so forth.

<table><caption>Keyboard location identifiers</caption><colgroup><col style="width: 33%" /><col style="width: 33%" /><col style="width: 33%" /></colgroup><thead><tr class="header"><th>Constant</th><th>Value</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>DOM_KEY_LOCATION_STANDARD</code></td><td>0x00</td><td><p>The key described by the event is not identified as being located in a particular area of the keyboard; it is not located on the numeric keypad (unless it's the NumLock key), and for keys that are duplicated on the left and right sides of the keyboard, the key is, for whatever reason, not to be associated with that location.</p><p>Examples include alphanumeric keys on the standard PC 101 US keyboard, the NumLock key, and the space bar.</p></td></tr><tr class="even"><td><code>DOM_KEY_LOCATION_LEFT</code></td><td>0x01</td><td><p>The key is one which may exist in multiple locations on the keyboard and, in this instance, is on the left side of the keyboard.</p><p>Examples include the left Control key, the left Command key on a Macintosh keyboard, or the left Shift key.</p></td></tr><tr class="odd"><td><code>DOM_KEY_LOCATION_RIGHT</code></td><td>0x02</td><td><p>The key is one which may exist in multiple positions on the keyboard and, in this case, is located on the right side of the keyboard.</p><p>Examples include the right Shift key and the right Alt key (Option on a Mac keyboard).</p></td></tr><tr class="even"><td><code>DOM_KEY_LOCATION_NUMPAD</code></td><td>0x03</td><td><p>The key is located on the numeric keypad, or is a virtual key associated with the numeric keypad if there's more than one place the key could originate from. The NumLock key does not fall into this group and is always encoded with the location <code>DOM_KEY_LOCATION_STANDARD</code>.</p><p>Examples include the digits on the numeric keypad, the keypad's Enter key, and the decimal point on the keypad.</p></td></tr></tbody></table>

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

*This interface also inherits properties of its parents, [`UIEvent`](https://developer.mozilla.org/en-US/docs/Web/API/UIEvent) and [`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event).*

[`KeyboardEvent.altKey`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/altKey) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that is `true` if the Alt ( Option or ⌥ on OS X) key was active when the key event was generated.

[`KeyboardEvent.code`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/code) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) with the code value of the physical key represented by the event.

**Warning:** This ignores the user's keyboard layout, so that if the user presses the key at the "Y" position in a QWERTY keyboard layout (near the middle of the row above the home row), this will always return "KeyY", even if the user has a QWERTZ keyboard (which would mean the user expects a "Z" and all the other properties would indicate a "Z") or a Dvorak keyboard layout (where the user would expect an "F").

[`KeyboardEvent.ctrlKey`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/ctrlKey) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that is `true` if the Ctrl key was active when the key event was generated.

[`KeyboardEvent.isComposing`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/isComposing) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that is `true` if the event is fired between after `compositionstart` and before `compositionend`.

[`KeyboardEvent.key`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/key) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) representing the key value of the key represented by the event.

<span class="page-not-created">`KeyboardEvent.locale`</span> <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) representing a locale string indicating the locale the keyboard is configured for. This may be the empty string if the browser or device doesn't know the keyboard's locale.

**Note:** This does not describe the locale of the data being entered. A user may be using one keyboard layout while typing text in a different language.

[`KeyboardEvent.location`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/location) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) representing the location of the key on the keyboard or other input device. A list of the constants identifying the locations is shown above in [Keyboard locations](#keyboard_locations).

[`KeyboardEvent.metaKey`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/metaKey) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that is `true` if the Meta key (on Mac keyboards, the ⌘ Command key; on Windows keyboards, the Windows key (⊞)) was active when the key event was generated.

[`KeyboardEvent.repeat`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/repeat) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that is `true` if the key is being held down such that it is automatically repeating.

[`KeyboardEvent.shiftKey`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/shiftKey) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that is `true` if the Shift key was active when the key event was generated.

[Methods](#methods "Permalink to Methods")
------------------------------------------

*This interface also inherits methods of its parents, [`UIEvent`](https://developer.mozilla.org/en-US/docs/Web/API/UIEvent) and [`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event).*

[`KeyboardEvent.getModifierState()`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/getModifierState)  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating if a modifier key such as Alt, Shift, Ctrl, or Meta, was pressed when the event was created.

[Obsolete methods](#obsolete_methods "Permalink to Obsolete methods")
---------------------------------------------------------------------

[`KeyboardEvent.initKeyEvent()`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/initKeyEvent)   
Initializes a `KeyboardEvent` object. This was implemented only by Firefox, and is no longer supported even there; instead, you should use the [`KeyboardEvent()`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/KeyboardEvent "KeyboardEvent()") constructor.

[`KeyboardEvent.initKeyboardEvent()`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/initKeyboardEvent)   
Initializes a `KeyboardEvent` object. This is now deprecated. You should instead use the [`KeyboardEvent()`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/KeyboardEvent "KeyboardEvent()") constructor.

[Obsolete properties](#obsolete_properties "Permalink to Obsolete properties")
------------------------------------------------------------------------------

<span class="page-not-created">`KeyboardEvent.char`</span> <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) representing the character value of the key. If the key corresponds to a printable character, this value is a non-empty Unicode string containing that character. If the key doesn't have a printable representation, this is an empty string.

**Note:** If the key is used as a macro that inserts multiple characters, this attribute's value is the entire string, not just the first character.

[`KeyboardEvent.charCode`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/charCode) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) representing the Unicode reference number of the key; this attribute is used only by the `keypress` event. For keys whose `char` attribute contains multiple characters, this is the Unicode value of the first character in that attribute. In Firefox 26 this returns codes for printable characters.

**Warning:** This attribute is deprecated; you should use [`KeyboardEvent.key`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/key) instead, if available.

[`KeyboardEvent.keyCode`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/keyCode) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) representing a system and implementation dependent numerical code identifying the unmodified value of the pressed key.

**Warning:** This attribute is deprecated; you should use [`KeyboardEvent.key`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/key) instead, if available.

[`KeyboardEvent.keyIdentifier`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/keyIdentifier) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
This property is non-standard and has been deprecated in favor of [`KeyboardEvent.key`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/key). It was part of an old version of DOM Level 3 Events.

<span class="page-not-created">`KeyboardEvent.keyLocation`</span> <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
This is a non-standard deprecated alias for [`KeyboardEvent.location`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/location). It was part of an old version of DOM Level 3 Events.

[`KeyboardEvent.which`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/which) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) representing a system and implementation dependent numeric code identifying the unmodified value of the pressed key; this is usually the same as `keyCode`.

**Warning:** This attribute is deprecated; you should use [`KeyboardEvent.key`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/key) instead, if available.

[Events](#events "Permalink to Events")
---------------------------------------

The following events are based on the `KeyboardEvent` type. They can be delivered to any object which implements [`GlobalEventHandlers`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers), including [`Element`](https://developer.mozilla.org/en-US/docs/Web/API/Element), [`Document`](https://developer.mozilla.org/en-US/docs/Web/API/Document), and [`Window`](https://developer.mozilla.org/en-US/docs/Web/API/Window). In the list below, each event links to the documentation for the `Document` handler for the event, which applies generally to all of the recipients.

[`keydown`](https://developer.mozilla.org/en-US/docs/Web/API/Document/keydown_event "keydown")  
A key has been pressed.

[`keyup`](https://developer.mozilla.org/en-US/docs/Web/API/Document/keyup_event "keyup")  
A key has been released.

### [Obsolete events](#obsolete_events "Permalink to Obsolete events")

[`keypress`](https://developer.mozilla.org/en-US/docs/Web/API/Document/keypress_event "keypress")   
A key that normally produces a character value has been pressed. This event was highly device-dependent and is obsolete. You should not use it.

[Usage notes](#usage_notes "Permalink to Usage notes")
------------------------------------------------------

There are three types of keyboard events: `keydown`, `keypress`, and `keyup`. For most keys, Gecko dispatches a sequence of key events like this:

1.  When the key is first pressed, the `keydown` event is sent.
2.  If the key is not a modifier key, the `keypress` event is sent.
3.  When the user releases the key, the `keyup` event is sent.

### [Special cases](#special_cases "Permalink to Special cases")

Some keys toggle the state of an indicator light; these include keys such as Caps Lock, Num Lock, and Scroll Lock. On Windows and Linux, these keys dispatch only the `keydown` and `keyup` events.

On Linux, Firefox 12 and earlier also dispatched the `keypress` event for these keys.

However, a limitation of the macOS event model causes Caps Lock to dispatch only the `keydown` event. Num Lock was supported on some older laptop models (2007 models and older), but since then, macOS hasn't supported Num Lock even on external keyboards. On older MacBooks with a Num Lock key, that key doesn't generate any key events. Gecko does support the Scroll Lock key if an external keyboard which has an F14 key is connected. In certain older versions of Firefox, this key generated a `keypress` event; this inconsistent behavior was <a href="https://bugzilla.mozilla.org/show_bug.cgi?id=602812" class="external">bug 602812</a>.

### [Auto-repeat handling](#auto-repeat_handling "Permalink to Auto-repeat handling")

When a key is pressed and held down, it begins to auto-repeat. This results in a sequence of events similar to the following being dispatched:

1.  `keydown`
2.  `keypress`
3.  `keydown`
4.  `keypress`
5.  &lt;&lt;repeating until the user releases the key&gt;&gt;
6.  `keyup`

This is what the DOM Level 3 specification says should happen. There are some caveats, however, as described below.

#### Auto-repeat on some GTK environments such as Ubuntu 9.4

In some GTK-based environments, auto-repeat dispatches a native key-up event automatically during auto-repeat, and there's no way for Gecko to know the difference between a repeated series of keypresses and an auto-repeat. On those platforms, then, an auto-repeat key will generate the following sequence of events:

1.  `keydown`
2.  `keypress`
3.  `keyup`
4.  `keydown`
5.  `keypress`
6.  `keyup`
7.  &lt;&lt;repeating until the user releases the key&gt;&gt;
8.  `keyup`

In these environments, unfortunately, there's no way for web content to tell the difference between auto-repeating keys and keys that are just being pressed repeatedly.

#### Auto-repeat handling prior to Gecko 5.0

Before Gecko 5.0 (Firefox 5.0 / Thunderbird 5.0 / SeaMonkey 2.2), keyboard handling was less consistent across platforms.

Windows  
Auto-repeat behavior is the same as in Gecko 4.0 and later.

Mac  
After the initial keydown event, only keypress events are sent until the keyup event occurs; the inter-spaced keydown events are not sent.

Linux  
The event behavior depends on the specific platform. It will either behave like Windows or Mac depending on what the native event model does.

**Note:** Manually firing an event does *not* generate the default action associated with that event. For example, manually firing a key event does not cause that letter to appear in a focused text input. In the case of UI events, this is important for security reasons, as it prevents scripts from simulating user actions that interact with the browser itself.

[Example](#example "Permalink to Example")
------------------------------------------

    <!DOCTYPE html>
    <html>
    <head>
    <script>
    'use strict';

    document.addEventListener('keydown', (event) => {
      const keyName = event.key;

      if (keyName === 'Control') {
        // do not alert when only Control key is pressed.
        return;
      }

      if (event.ctrlKey) {
        // Even though event.key is not 'Control' (e.g., 'a' is pressed),
        // event.ctrlKey may be true if Ctrl key is pressed at the same time.
        alert(`Combination of ctrlKey + ${keyName}`);
      } else {
        alert(`Key pressed ${keyName}`);
      }
    }, false);

    document.addEventListener('keyup', (event) => {
      const keyName = event.key;

      // As the user releases the Ctrl key, the key is no longer active,
      // so event.ctrlKey is false.
      if (keyName === 'Control') {
        alert('Control key was released');
      }
    }, false);

    </script>
    </head>

    <body>
    </body>
    </html>

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/uievents/#interface-keyboardevent" class="external">UI Events<br />
<span class="small">The definition of 'KeyboardEvent' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

The `KeyboardEvent` interface specification went through numerous draft versions, first under DOM Events Level 2 where it was dropped as no consensus arose, then under DOM Events Level 3. This led to the implementation of non-standard initialization methods, the early DOM Events Level 2 version, [`KeyboardEvent.initKeyEvent()`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/initKeyEvent) by Gecko browsers and the early DOM Events Level 3 version, [`KeyboardEvent.initKeyboardEvent()`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/initKeyboardEvent) by others. Both have been superseded by the modern usage of a constructor: [`KeyboardEvent()`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/KeyboardEvent "KeyboardEvent()").

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

### [Compatibility notes](#compatibility_notes "Permalink to Compatibility notes")

-   As of Firefox 65, the `keypress` event is no longer fired for [non-printable keys](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/keyCode#non-printable_keys_(function_keys)) (<a href="https://bugzilla.mozilla.org/show_bug.cgi?id=968056" class="external">bug 968056</a>), except for the Enter key, and the Shift + Enter and Ctrl + Enter key combinations (these were kept for cross-browser compatibility purposes).

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [`KeyboardEvent.code`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/code).
-   [`KeyboardEvent.key`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/key).
-   [`KeyboardEvent.getModifierState()`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/getModifierState)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/keyboardevent/index.html "Folder: en-us/web/api/keyboardevent (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FKeyboardEvent%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fkeyboardevent%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FKeyboardEvent%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fkeyboardevent%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fb06b69b145b54e5a4d7240a3363b345c42b3294e%0A*+Document+last+modified%3A+2021-05-31T16%3A54%3A27.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22KeyboardEvent%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/contributors.txt)

Change your languageSelect your preferred language English (US)DeutschEspañolFrançais日本語Português (do Brasil)Русский中文 (简体)正體中文 (繁體)

Change language

#### Related Topics

1.  **[`KeyboardEvent`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent)**
2.  Constructor
    1.  [`KeyboardEvent()`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/KeyboardEvent)
3.  Properties
    1.  [`altKey`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/altKey)
    2.  [`charCode`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/charCode)
    3.  [`code`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/code)
    4.  [`ctrlKey`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/ctrlKey)
    5.  [`isComposing`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/isComposing)
    6.  [`key`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/key)
    7.  [`keyCode`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/keyCode)
    8.  [`keyIdentifier`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/keyIdentifier)
    9.  [`location`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/location)
    10. [`metaKey`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/metaKey)
    11. [`repeat`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/repeat)
    12. [`shiftKey`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/shiftKey)
    13. [`which`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/which)
4.  Methods
    1.  [`getModifierState()`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/getModifierState)
    2.  [`initKeyboardEvent()`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/initKeyboardEvent)
    3.  [`initKeyEvent()`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/initKeyEvent)
5.  Inheritance:
    1.  [`UIEvent`](https://developer.mozilla.org/en-US/docs/Web/API/UIEvent)
    2.  [`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event)
6.  Related pages for DOM Events
    1.  [`CompositionEvent`](https://developer.mozilla.org/en-US/docs/Web/API/CompositionEvent)
    2.  [`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event)
    3.  [`EventListener`](https://developer.mozilla.org/en-US/docs/Web/API/EventListener)
    4.  [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)
    5.  [`FocusEvent`](https://developer.mozilla.org/en-US/docs/Web/API/FocusEvent)
    6.  [`InputEvent`](https://developer.mozilla.org/en-US/docs/Web/API/InputEvent)
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
