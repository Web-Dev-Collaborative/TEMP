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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement" class="breadcrumb-current-page"><span data-property="name">HTMLFormElement</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Properties](#properties)
-   [Methods](#methods)
-   [Events](#events)
-   [Usage notes](#usage_notes)
-   [Examples](#examples)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

HTMLFormElement
===============

<span class="seoSummary">The `HTMLFormElement` interface represents a [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form) element in the DOM. It allows access to—and, in some cases, modification of—aspects of the form, as well as access to its component elements.</span>

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

*This interface also inherits properties from its parent, [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement).*

[`HTMLFormElement.elements`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/elements) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
A [`HTMLFormControlsCollection`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormControlsCollection) holding all form controls belonging to this form element.

[`HTMLFormElement.length`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/length)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
A `long` reflecting the number of controls in the form.

[`HTMLFormElement.name`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/name)  
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the value of the form's [`name`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form#attr-name) HTML attribute, containing the name of the form.

[`HTMLFormElement.method`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/method)  
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the value of the form's [`method`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form#attr-method) HTML attribute, indicating the HTTP method used to submit the form. Only specified values can be set.

[`HTMLFormElement.target`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/target)  
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the value of the form's [`target`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form#attr-target) HTML attribute, indicating where to display the results received from submitting the form.

[`HTMLFormElement.action`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/action)  
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the value of the form's [`action`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form#attr-action) HTML attribute, containing the URI of a program that processes the information submitted by the form.

[`HTMLFormElement.encoding`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/encoding) or [`HTMLFormElement.enctype`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/enctype)  
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the value of the form's [`enctype`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form#attr-enctype) HTML attribute, indicating the type of content that is used to transmit the form to the server. Only specified values can be set. The two properties are synonyms.

[`HTMLFormElement.acceptCharset`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/acceptCharset)  
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the value of the form's [`accept-charset`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form#attr-accept-charset) HTML attribute, representing the character encoding that the server accepts.

<span class="page-not-created">`HTMLFormElement.autocomplete`</span>  
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) reflecting the value of the form's [`autocomplete`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form#attr-autocomplete) HTML attribute, indicating whether the controls in this form can have their values automatically populated by the browser.

<span class="page-not-created">`HTMLFormElement.noValidate`</span>  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) reflecting the value of the form's [`novalidate`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form#attr-novalidate) HTML attribute, indicating whether the form should not be validated.

Named inputs are added to their owner form instance as properties, and can overwrite native properties if they share the same name (e.g. a form with an input named `action` will have its `action` property return that input instead of the form's [`action`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form#attr-action) HTML attribute).

[Methods](#methods "Permalink to Methods")
------------------------------------------

*This interface also inherits methods from its parent, [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement).*

<span class="page-not-created">`checkValidity()`</span>  
Returns `true` if the element's child controls are subject to [constraint validation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Constraint_validation) and satisfy those constraints; returns `false` if some controls do not satisfy their constraints. Fires an event named [`invalid`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/invalid_event "invalid") at any control that does not satisfy its constraints; such controls are considered invalid if the event is not canceled. It is up to the programmer to decide how to respond to `false`.

[`reportValidity()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/reportValidity "reportValidity()")  
Returns `true` if the element's child controls satisfy their [validation constraints](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Constraint_validation). When `false` is returned, cancelable [`invalid`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/invalid_event "invalid") events are fired for each invalid child and validation problems are reported to the user.

[`requestSubmit()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/requestSubmit "requestSubmit()")  
Requests that the form be submitted using the specified submit button and its corresponding configuration.

[`reset()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/reset "reset()")  
Resets the form to its initial state.

[`submit()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/submit "submit()")  
Submits the form to the server.

### [Deprecated methods](#deprecated_methods "Permalink to Deprecated methods")

<span class="page-not-created">`HTMLFormElement.requestAutocomplete()`</span>   
Triggers a native browser interface to assist the user in completing the fields which have an <a href="https://html.spec.whatwg.org/#autofill-field-name" class="external">autofill field name</a> value that is not `off` or `on`. The form will receive an event once the user has finished with the interface, the event will either be `autocomplete` when the fields have been filled or `autocompleteerror` when there was a problem.

[Events](#events "Permalink to Events")
---------------------------------------

Listen to these events using `addEventListener()`, or by assigning an event listener to the `oneventname` property of this interface.

[`formdata`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/formdata_event "formdata")  
The `formdata` event fires after the entry list representing the form's data is constructed.  
Also available via the [`onformdata`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onformdata "onformdata") property.

[`reset`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/reset_event "reset")  
The `reset` event fires when a form is reset.  
Also available via the [`onreset`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onreset "onreset") property.

[`submit`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/submit_event "submit")  
The `submit` event fires when a form is submitted.  
Also available via the [`onsubmit`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onsubmit "onsubmit") property.

[Usage notes](#usage_notes "Permalink to Usage notes")
------------------------------------------------------

### [Obtaining a form element object](#obtaining_a_form_element_object "Permalink to Obtaining a form element object")

To obtain an `HTMLFormElement` object, you can use a [CSS selector](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors) with [`querySelector()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector "querySelector()"), or you can get a list of all of the forms in the document using its [`forms`](https://developer.mozilla.org/en-US/docs/Web/API/Document/forms "forms") property.

[`Document.forms`](https://developer.mozilla.org/en-US/docs/Web/API/Document/forms) returns an array of `HTMLFormElement` objects listing each of the forms on the page. You can then use any of the following syntaxes to get an individual form:

`document.forms[index]`  
Returns the form at the specified `index` into the array of forms.

`document.forms[id]`  
Returns the form whose ID is `id`.

`document.forms[name]`  
Returns the form whose [`name`](https://developer.mozilla.org/en-US/docs/Web/API "name") attribute's value is `name`.

### [Accessing the form's elements](#accessing_the_forms_elements "Permalink to Accessing the form's elements")

You can access the list of the form's data-containing elements by examining the form's [`elements`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/elements "elements") property. This returns an [`HTMLFormControlsCollection`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormControlsCollection) listing all of the form's user data entry elements, both those which are descendants of the `<form>` and those which are made members of the form using their `form` attributes.

You can also get the form's element by using its `name` attribute as a key of the `form`, but using `elements` is a better approach—it contains *only* the form's elements, and it cannot be mixed with other attributes of the `form`.

### [Issues with Naming Elements](#issues_with_naming_elements "Permalink to Issues with Naming Elements")

Some names will interfere with JavaScript access to the form’s properties and elements.

For example:

-   `<input name="id">` will take precedence over `<form id="…">`. This means that `form.id` will not refer to the form’s id, but to the element whose name is "`id`". This will be the case with any other form properties, such as `<input name="action">` or `<input name="post">`.
-   `<input name="elements">` will render the form’s `elements` collection inaccessible. The reference `form.elements` will now refer to the individual element.

To avoid such problems with element names:

-   *Always* use the `elements` collection to avoid ambiguity between an element name and a form property.
-   *Never* use "`elements`" as an element name.

If you are not using JavaScript, this will not cause a problem.

### [Elements that are considered form controls](#elements_that_are_considered_form_controls "Permalink to Elements that are considered form controls")

The elements included by `HTMLFormElement.elements` and `HTMLFormElement.length` are the following:

-   [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button)
-   [`<fieldset>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/fieldset)
-   [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) (with the exception that any whose [`type`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-type) is `"image"` are omitted for historical reasons)
-   [`<object>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/object)
-   [`<output>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/output)
-   [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select)
-   [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea)

No other elements are included in the list returned by `elements`, which makes it an excellent way to get at the elements most important when processing forms.

[Examples](#examples "Permalink to Examples")
---------------------------------------------

Creating a new form element, modifying its attributes, then submitting it:

    const f = document.createElement("form"); // Create a form
    document.body.appendChild(f);             // Add it to the document body
    f.action = "/cgi-bin/some.cgi";           // Add action and method attributes
    f.method = "POST";
    f.submit();                               // Call the form's submit() method

Extract information from a `<form>` element and set some of its attributes:

    <form name="formA" action="/cgi-bin/test" method="post">
     <p>Press "Info" for form details, or "Set" to change those details.</p>
     <p>
      <button type="button" onclick="getFormInfo();">Info</button>
      <button type="button" onclick="setFormInfo(this.form);">Set</button>
      <button type="reset">Reset</button>
     </p>

     <textarea id="form-info" rows="15" cols="20"></textarea>
    </form>

    <script>
      function getFormInfo(){
        // Get a reference to the form via its name
        var f = document.forms["formA"];
        // The form properties we're interested in
        var properties = [ 'elements', 'length', 'name', 'charset', 'action', 'acceptCharset', 'action', 'enctype', 'method', 'target' ];
        // Iterate over the properties, turning them into a string that we can display to the user
        var info = properties.map(function(property) { return property + ": " + f[property] }).join("\n");

        // Set the form's <textarea> to display the form's properties
        document.forms["formA"].elements['form-info'].value = info; // document.forms["formA"]['form-info'].value would also work
      }

      function setFormInfo(f){ // Argument should be a form element reference.
        f.action = "a-different-url.cgi";
        f.name   = "a-different-name";
      }
    </script>

Submit a `<form>` into a new window:

    <!doctype html>
    <html>
    <head>
    <meta charset="utf-8">
    <title>Example new-window form submission</title>
    </head>
    <body>

    <form action="test.php" target="_blank">
      <p><label>First name: <input type="text" name="firstname"></label></p>
      <p><label>Last name: <input type="text" name="lastname"></label></p>
      <p><label><input type="password" name="pwd"></label></p>

      <fieldset>
       <legend>Pet preference</legend>

        <p><label><input type="radio" name="pet" value="cat"> Cat</label></p>
        <p><label><input type="radio" name="pet" value="dog"> Dog</label></p>
      </fieldset>

      <fieldset>
        <legend>Owned vehicles</legend>

        <p><label><input type="checkbox" name="vehicle" value="Bike">I have a bike</label></p>
        <p><label><input type="checkbox" name="vehicle" value="Car">I have a car</label></p>
      </fieldset>

      <p><button>Submit</button></p>
    </form>

    </body>
    </html>

### [Submitting forms and uploading files using XMLHttpRequest](#submitting_forms_and_uploading_files_using_xmlhttprequest "Permalink to Submitting forms and uploading files using XMLHttpRequest")

If you want to know how to serialize and submit a form using the [`XMLHttpRequest`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest) API, please read [this paragraph](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/Using_XMLHttpRequest#submitting_forms_and_uploading_files).

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#htmlformelement" class="external">HTML Living Standard<br />
<span class="small">The definition of 'HTMLFormElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>The following method has been added: <code>requestAutocomplete()</code>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/sec-forms.html#htmlformelement" class="external">HTML5<br />
<span class="small">The definition of 'HTMLFormElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>The elements properties returns an <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormControlsCollection"><code>HTMLFormControlsCollection</code></a> instead of a raw <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLCollection"><code>HTMLCollection</code></a>. This is mainly a technical change. The following method has been added: <code>checkValidity()</code>. The following properties have been added: <code>autocomplete</code>, <code>noValidate</code>, and <code>encoding</code>.</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   The HTML element implementing this interface: [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form).

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/htmlformelement/index.html "Folder: en-us/web/api/htmlformelement (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FHTMLFormElement%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fhtmlformelement%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FHTMLFormElement%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fhtmlformelement%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fcb20a8045f6cbdbd224b1068e46c8644470dd8c3%0A*+Document+last+modified%3A+2021-06-01T09%3A10%3A31.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22HTMLFormElement%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Jun 1, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/contributors.txt)

Change your languageSelect your preferred language English (US)DeutschEspañolFrançais日本語한국어PolskiРусский中文 (简体)正體中文 (繁體)

Change language

#### Related Topics

1.  **[`HTMLFormElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement)**
2.  Properties
    1.  [`acceptCharset`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/acceptCharset)
    2.  [`action`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/action)
    3.  [`elements`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/elements)
    4.  [`encoding`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/encoding)
    5.  [`enctype`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/enctype)
    6.  [`length`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/length)
    7.  [`method`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/method)
    8.  [`name`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/name)
    9.  [`target`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/target)
3.  Methods
    1.  [`reportValidity()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/reportValidity)
    2.  [`requestSubmit()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/requestSubmit)
    3.  [`reset()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/reset)
    4.  [`submit()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/submit)
4.  Events
    1.  [`formdata`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/formdata_event)
    2.  [`reset`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/reset_event)
    3.  [`submit`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/submit_event)
5.  Inheritance:
    1.  [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
    2.  [`Element`](https://developer.mozilla.org/en-US/docs/Web/API/Element)
    3.  [`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node)
    4.  [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)
6.  Related pages for HTML DOM
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
    25. [`HTMLFrameSetElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFrameSetElement)
    26. [`HTMLHRElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLHRElement)
    27. [`HTMLHeadElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLHeadElement)
    28. [`HTMLHeadingElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLHeadingElement)
    29. [`HTMLHtmlElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLHtmlElement)
    30. [`HTMLIFrameElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLIFrameElement)
    31. [`HTMLImageElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement)
    32. [`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement)
    33. [`HTMLIsIndexElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLIsIndexElement)
    34. [`HTMLKeygenElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLKeygenElement)
    35. [`HTMLLIElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLLIElement)
    36. [`HTMLLabelElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLLabelElement)
    37. [`HTMLLegendElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLLegendElement)
    38. [`HTMLLinkElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLLinkElement)
    39. [`HTMLMapElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMapElement)
    40. [`HTMLMediaElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement)
    41. [`HTMLMetaElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMetaElement)
    42. [`HTMLMeterElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMeterElement)
    43. [`HTMLModElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLModElement)
    44. [`HTMLOListElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOListElement)
    45. [`HTMLObjectElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLObjectElement)
    46. [`HTMLOptGroupElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOptGroupElement)
    47. [`HTMLOptionElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOptionElement)
    48. [`HTMLOptionsCollection`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOptionsCollection)
    49. [`HTMLOutputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOutputElement)
    50. [`HTMLParagraphElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLParagraphElement)
    51. [`HTMLParamElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLParamElement)
    52. [`HTMLPictureElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLPictureElement)
    53. [`HTMLPreElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLPreElement)
    54. [`HTMLProgressElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLProgressElement)
    55. [`HTMLQuoteElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLQuoteElement)
    56. [`HTMLScriptElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLScriptElement)
    57. [`HTMLSelectElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement)
    58. [`HTMLShadowElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLShadowElement)
    59. [`HTMLSourceElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSourceElement)
    60. [`HTMLSpanElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSpanElement)
    61. [`HTMLStyleElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLStyleElement)
    62. [`HTMLTableCaptionElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableCaptionElement)
    63. [`HTMLTableCellElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableCellElement)
    64. [`HTMLTableColElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableColElement)
    65. [`HTMLTableDataCellElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableDataCellElement)
    66. [`HTMLTableElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableElement)
    67. [`HTMLTableHeaderCellElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableHeaderCellElement)
    68. [`HTMLTableRowElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableRowElement)
    69. [`HTMLTableSectionElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableSectionElement)
    70. [`HTMLTemplateElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTemplateElement)
    71. [`HTMLTextAreaElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTextAreaElement)
    72. [`HTMLTimeElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTimeElement)
    73. [`HTMLTitleElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTitleElement)
    74. [`HTMLTrackElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTrackElement)
    75. [`HTMLUListElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLUListElement)
    76. [`HTMLUnknownElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLUnknownElement)
    77. [`HTMLVideoElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLVideoElement)
    78. [`HashChangeEvent`](https://developer.mozilla.org/en-US/docs/Web/API/HashChangeEvent)
    79. [`History`](https://developer.mozilla.org/en-US/docs/Web/API/History)
    80. [`ImageData`](https://developer.mozilla.org/en-US/docs/Web/API/ImageData)
    81. [`Location`](https://developer.mozilla.org/en-US/docs/Web/API/Location)
    82. [`MessageChannel`](https://developer.mozilla.org/en-US/docs/Web/API/MessageChannel)
    83. [`MessageEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MessageEvent)
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
-   [Terms](https://www.mozilla.org/about/legal/terms/mozilla)
-   [Privacy](https://www.mozilla.org/privacy/websites/)
-   [Cookies](https://www.mozilla.org/privacy/websites/#cookies)
