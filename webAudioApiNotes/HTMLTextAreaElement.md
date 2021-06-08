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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLTextAreaElement" class="breadcrumb-current-page"><span data-property="name">HTMLTextAreaElement</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Properties](#properties)
-   [Methods](#methods)
-   [Events](#events)
-   [Examples](#examples)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)

HTMLTextAreaElement
===================

The **`HTMLTextAreaElement`** interface provides special properties and methods for manipulating the layout and presentation of [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea) elements.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><code>accessKey</code></td><td><code>string:</code> Returns / Sets the element's <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea#attr-accesskey"><code>accesskey</code></a> attribute.</td></tr><tr class="even"><td><code>autocapitalize</code></td><td><code>string:</code> Returns / Sets the element's capitalization behavior for user input. Valid values are: <code>none</code>, <code>off</code>, <code>characters</code>, <code>words</code>, <code>sentences</code>.</td></tr><tr class="odd"><td><code>autocomplete</code></td><td></td></tr><tr class="even"><td><code>autofocus</code></td><td><code>boolean:</code> Returns / Sets the element's <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea#attr-autofocus"><code>autofocus</code></a> attribute, indicating that the control should have input focus when the page loads</td></tr><tr class="odd"><td><code>cols</code></td><td><code>unsigned long:</code> Returns / Sets the element's <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea#attr-cols"><code>cols</code></a> attribute, indicating the visible width of the text area.</td></tr><tr class="even"><td><code>defaultValue</code></td><td><code>string:</code> Returns / Sets the control's default value, which behaves like the <a href="https://developer.mozilla.org/en-US/docs/Web/API/Node/textContent"><code>Node.textContent</code></a> property.</td></tr><tr class="odd"><td><code>disabled</code></td><td><code>boolean:</code> Returns / Sets the element's <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea#attr-disabled"><code>disabled</code></a> attribute, indicating that the control is not available for interaction.</td></tr><tr class="even"><td><code>form</code> <span class="badge inline readonly" title="This value may not be changed.">Read only </span></td><td><code>object:</code> Returns a reference to the parent form element. If this element is not contained in a form element, it can be the <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form#attr-id"><code>id</code></a> attribute of any <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form"><code>&lt;form&gt;</code></a> element in the same document or the value <code>null</code>.</td></tr><tr class="odd"><td><code>inputMode</code></td><td></td></tr><tr class="even"><td><code>maxLength</code></td><td><code>long:</code> Returns / Sets the element's <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea#attr-maxlength"><code>maxlength</code></a> attribute, indicating the maximum number of characters the user can enter. This constraint is evaluated only when the value changes.</td></tr><tr class="odd"><td><code>minLength</code></td><td><code>long:</code> Returns / Sets the element's <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea#attr-minlength"><code>minlength</code></a> attribute, indicating the minimum number of characters the user can enter. This constraint is evaluated only when the value changes.</td></tr><tr class="even"><td><code>name</code></td><td><code>string:</code> Returns / Sets the element's <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea#attr-name"><code>name</code></a> attribute, containing the name of the control.</td></tr><tr class="odd"><td><code>placeholder</code></td><td><code>string:</code> Returns / Sets the element's <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea#attr-placeholder"><code>placeholder</code></a> attribute, containing a hint to the user about what to enter in the control.</td></tr><tr class="even"><td><code>readOnly</code></td><td><code>boolean:</code> Returns / Sets the element's <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea#attr-readonly"><code>readonly</code></a> attribute, indicating that the user cannot modify the value of the control.</td></tr><tr class="odd"><td><code>required</code></td><td><code>boolean:</code> Returns / Sets the element's <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea#attr-required"><code>required</code></a> attribute, indicating that the user must specify a value before submitting the form.</td></tr><tr class="even"><td><code>rows</code></td><td><code>unsigned long:</code> Returns / Sets the element's <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea#attr-rows"><code>rows</code></a> attribute, indicating the number of visible text lines for the control.</td></tr><tr class="odd"><td><code>selectionDirection</code></td><td><code>string:</code> Returns / Sets the direction in which selection occurred. This is "<code>forward</code>" if selection was performed in the start-to-end direction of the current locale, or "<code>backward</code>" for the opposite direction. This can also be "<code>none</code>" if the direction is unknown.</td></tr><tr class="even"><td><code>selectionEnd</code></td><td><code>unsigned long:</code> Returns / Sets the index of the end of selected text. If no text is selected, contains the index of the character that follows the input cursor. On being set, the control behaves as if <code>setSelectionRange()</code> had been called with this as the second argument, and <code>selectionStart</code> as the first argument.</td></tr><tr class="odd"><td><code>selectionStart</code></td><td><code>unsigned long:</code> Returns / Sets the index of the beginning of selected text. If no text is selected, contains the index of the character that follows the input cursor. On being set, the control behaves as if <code>setSelectionRange()</code> had been called with this as the first argument, and <code>selectionEnd</code> as the second argument.</td></tr><tr class="even"><td><code>tabIndex</code></td><td><code>long:</code> Returns / Sets the position of the element in the tabbing navigation order for the current document.</td></tr><tr class="odd"><td><code>textLength</code> <span class="badge inline readonly" title="This value may not be changed.">Read only </span></td><td><code>long:</code> Returns the codepoint length of the control's <code>value</code>. Same as reading <code>value.length</code></td></tr><tr class="even"><td><code>type</code> <span class="badge inline readonly" title="This value may not be changed.">Read only </span></td><td><code>string:</code> Returns the string <code>textarea</code>.</td></tr><tr class="odd"><td><code>validationMessage</code> <span class="badge inline readonly" title="This value may not be changed.">Read only </span></td><td><code>string:</code> Returns a localized message that describes the validation constraints that the control does not satisfy (if any). This is the empty string if the control is not a candidate for constraint validation (<code>willValidate</code> is <code>false</code>), or it satisfies its constraints.</td></tr><tr class="even"><td><code>validity</code> <span class="badge inline readonly" title="This value may not be changed.">Read only </span></td><td><code>ValidityState</code> object: Returns the validity states that this element is in.</td></tr><tr class="odd"><td><code>value</code></td><td><code>string:</code> Returns / Sets the raw value contained in the control.</td></tr><tr class="even"><td><code>willValidate</code> <span class="badge inline readonly" title="This value may not be changed.">Read only </span></td><td><p><code>boolean:</code> Returns whether the element is a candidate for constraint validation. <code>false</code> if any conditions bar it from constraint validation, including its <code>readOnly</code> or <code>disabled</code> property is <code>true</code>.</p></td></tr><tr class="odd"><td><code>wrap</code></td><td><code>string:</code> Returns / Sets the <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea#attr-wrap"><code>wrap</code></a> HTML attribute, indicating how the control wraps text.</td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLTextAreaElement/labels"><code>HTMLTextAreaElement.labels</code></a><span class="badge inline readonly" title="This value may not be changed.">Read only </span></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/NodeList"><code>NodeList</code></a>: Returns a list of label elements associated with this element.</td></tr></tbody></table>

The two properties `tabIndex` and `accessKey` are inherited from [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement) from HTML5 on, but were defined on `HTMLTextAreaElement` in DOM Level 2 HTML and earlier specifications.

[Methods](#methods "Permalink to Methods")
------------------------------------------

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLOrForeignElement/blur" title="blur()"><code>blur()</code></a></td><td>Removes focus from the control; keystrokes will subsequently go nowhere.</td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLOrForeignElement/focus" title="focus()"><code>focus()</code></a></td><td>Gives focus to the control; keystrokes will subsequently go to this element.</td></tr><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/select" title="select()"><code>select()</code></a></td><td>Selects the contents of the control.</td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/setRangeText" title="setRangeText()"><code>setRangeText()</code></a></td><td>Replaces a range of text in the element with new text.</td></tr><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/setSelectionRange" title="setSelectionRange()"><code>setSelectionRange()</code></a></td><td>Selects a range of text in the element (but does not focus it).</td></tr><tr class="even"><td><code>checkValidity()</code></td><td>Returns <code>false</code> if the element is a candidate for constraint validation, and it does not satisfy its constraints. In this case, it also fires a cancelable <code>invalid</code> event at the control. It returns <code>true</code> if the control is not a candidate for constraint validation, or if it satisfies its constraints.</td></tr><tr class="odd"><td><code>reportValidity()</code></td><td><p>This method reports the problems with the constraints on the element, if any, to the user. If there are problems, it fires a cancelable <code>invalid</code> event at the element, and returns <code>false</code>; if there are no problems, it returns <code>true</code>.</p></td></tr><tr class="even"><td><code>setCustomValidity(DOMstring)</code></td><td>Sets a custom validity message for the element. If this message is not the empty string, then the element is suffering from a custom validity error, and does not validate.</td></tr></tbody></table>

The two methods `blur()` and `focus()` are inherited from [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement) from HTML5 on, but were defined on `HTMLTextAreaElement` in DOM Level 2 HTML and earlier specifications.

[Events](#events "Permalink to Events")
---------------------------------------

Listen to these events using [`addEventListener()`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener "addEventListener()") or by assigning an event listener to the `oneventname` property of this interface:

[`input`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/input_event "input") event  
Fires when the `value` of an [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input), [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select), or [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea) element has been changed.

[Examples](#examples "Permalink to Examples")
---------------------------------------------

### [Autogrowing textarea example](#autogrowing_textarea_example "Permalink to Autogrowing textarea example")

Make a textarea autogrow while typing:

#### JavaScript

    function autoGrow (oField) {
      if (oField.scrollHeight > oField.clientHeight) {
        oField.style.height = oField.scrollHeight + "px";
      }
    }

#### CSS

    textarea.noscrollbars {
      overflow: hidden;
      width: 300px;
      height: 100px;
    }

#### HTML

    <form>
      <fieldset>
        <legend>Your comments</legend>
        <p><textarea class="noscrollbars" onkeyup="autoGrow(this);"></textarea></p>
        <p><input type="submit" value="Send" /></p>
      </fieldset>
    </form>

### [Insert HTML tags example](#insert_html_tags_example "Permalink to Insert HTML tags example")

Insert some HTML tags or *smiles* or any custom text in a textarea.

#### JavaScript

    function insertMetachars(sStartTag, sEndTag) {
      var bDouble = arguments.length > 1, oMsgInput = document.myForm.myTxtArea, nSelStart = oMsgInput.selectionStart, nSelEnd = oMsgInput.selectionEnd, sOldText = oMsgInput.value;
      oMsgInput.value = sOldText.substring(0, nSelStart) + (bDouble ? sStartTag + sOldText.substring(nSelStart, nSelEnd) + sEndTag : sStartTag) + sOldText.substring(nSelEnd);
      oMsgInput.setSelectionRange(bDouble || nSelStart === nSelEnd ? nSelStart + sStartTag.length : nSelStart, (bDouble ? nSelEnd : nSelStart) + sStartTag.length);
      oMsgInput.focus();
    }

#### CSS

CSS to decorate the internal span to behave like a link:

    .intLink {
      cursor: pointer;
      text-decoration: underline;
      color: #0000ff;
    }

HTML:

    <form name="myForm">
    <p>[&nbsp;<span class="intLink" onclick="insertMetachars('&lt;strong&gt;','&lt;\/strong&gt;');"><strong>Bold</strong></span> | <span class="intLink" onclick="insertMetachars('&lt;em&gt;','&lt;\/em&gt;');"><em>Italic</em></span> | <span class="intLink" onclick="var newURL=prompt('Enter the full URL for the link');if(newURL){insertMetachars('&lt;a href=\u0022'+newURL+'\u0022&gt;','&lt;\/a&gt;');}else{document.myForm.myTxtArea.focus();}">URL</span> | <span class="intLink" onclick="insertMetachars('\n&lt;code&gt;\n','\n&lt;\/code&gt;\n');">code</span> | <span class="intLink" onclick="insertMetachars(' :-)');">smile</span> | etc. etc.&nbsp;]</p>
    <p><textarea name="myTxtArea" rows="10" cols="50">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut facilisis, arcu vitae adipiscing placerat, nisl lectus accumsan nisi, vitae iaculis sem neque vel lectus. Praesent tristique commodo lorem quis fringilla. Sed ac tellus eros. Sed consectetur eleifend felis vitae luctus. Praesent sagittis, est eget bibendum tincidunt, ligula diam tincidunt augue, a fermentum odio velit eget mi. Phasellus mattis, elit id fringilla semper, orci magna cursus ligula, non venenatis lacus augue sit amet dui. Pellentesque lacinia odio id nisi pulvinar commodo tempus at odio. Ut consectetur eros porttitor nunc mollis ultrices. Aenean porttitor, purus sollicitudin viverra auctor, neque erat blandit sapien, sit amet tincidunt massa mi ac nibh. Proin nibh sem, bibendum ut placerat nec, cursus et lacus. Phasellus vel augue turpis. Nunc eu mauris eu leo blandit mollis interdum eget lorem. </textarea></p>
    </form>

### [Maximum length and number of lines example](#maximum_length_and_number_of_lines_example "Permalink to Maximum length and number of lines example")

Create a textarea with a maximum number of characters per line and a maximum number of lines:

First, create a function that takes the text field and a key event as input and determines if any of the limits have been reached. If the limit has not been reached, it will return the key.

    function checkRows(oField, oKeyEvent) {
      var nKey = (oKeyEvent || /* old IE */ window.event || /* check is not supported! */ { keyCode: 38 }).keyCode,

        // put here the maximum number of characters per line:
        nCols = 30,
        // put here the maximum number of lines:
        nRows = 5,

        nSelS = oField.selectionStart, nSelE = oField.selectionEnd,
        sVal = oField.value, nLen = sVal.length,

        nBackward = nSelS >= nCols ? nSelS - nCols : 0,
        nDeltaForw = sVal.substring(nBackward, nSelS).search(new RegExp("\\n(?!.{0," + String(nCols - 2) + "}\\n)")) + 1,
        nRowStart = nBackward + nDeltaForw,
        aReturns = (sVal.substring(0, nSelS) + sVal.substring(nSelE, sVal.length)).match(/\n/g),
        nRowEnd = nSelE + nRowStart + nCols - nSelS,
        sRow = sVal.substring(nRowStart, nSelS) + sVal.substring(nSelE, nRowEnd > nLen ? nLen : nRowEnd),
        bKeepCols = nKey === 13 || nLen + 1 < nCols || /\n/.test(sRow) || ((nRowStart === 0 || nDeltaForw > 0 || nKey > 0) && (sRow.length < nCols || (nKey > 0 && (nLen === nRowEnd || sVal.charAt(nRowEnd) === "\n"))));

      return (nKey !== 13 || (aReturns ? aReturns.length + 1 : 1) < nRows) && ((nKey > 32 && nKey < 41) || bKeepCols);
    }

In the HTML we just need to hook our function to the \`onkeypress\` event and specify that our textarea does not accept pasting:

    <form>
      <p>Textarea with fixed number of characters per line:<br />
        <textarea cols="50" rows="10" onkeypress="return checkRows(this, event);"
                  onpaste="return false;"></textarea>
      </p>
    </form>

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#htmltextareaelement" class="external">HTML Living Standard<br />
<span class="small">The definition of 'HTMLTextAreaElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/forms.html#the-textarea-element" class="external">HTML5<br />
<span class="small">The definition of 'HTMLTextAreaElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>The attributes <code>tabindex</code> and <code>accesskey</code>, as well as the methods <code>blur()</code> and <code>focus()</code> are now defined on <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement"><code>HTMLElement</code></a>.<br />
The following attributes have been added: <code>autofocus</code>, <code>placeholder</code>, <code>dirName</code>, <code>wrap</code>, <code>maxLength</code>, <code>required</code>, <code>textLength</code>, <code>labels</code>, <code>selectionStart</code>, <code>selectionEnd</code>, <code>selectionDirection</code>, <code>validity</code>, <code>validationMessage</code>, and <code>willValidate</code>.<br />
The following methods have been added: <code>checkValidity()</code>, <code>setCustomValidity()</code>, and <code>setSelectionRange()</code>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-ID-24874179" class="external">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'HTMLTextAreaElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>The property <code>defaultValue</code> doesn't contain the initial value of the <code>value</code> attribute, but the initial value of the content of the <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea"><code>&lt;textarea&gt;</code></a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-html.html#ID-24874179" class="external">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'HTMLTextAreaElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/htmltextareaelement/index.html "Folder: en-us/web/api/htmltextareaelement (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FHTMLTextAreaElement%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fhtmltextareaelement%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FHTMLTextAreaElement%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fhtmltextareaelement%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fcb20a8045f6cbdbd224b1068e46c8644470dd8c3%0A*+Document+last+modified%3A+2021-06-01T09%3A10%3A31.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22HTMLTextAreaElement%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Jun 1, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTextAreaElement/contributors.txt)

Change your languageSelect your preferred language English (US)日本語中文 (简体)

Change language

#### Related Topics

1.  **[`HTMLTextAreaElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTextAreaElement)**
2.  Properties
    1.  [`labels`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTextAreaElement/labels)
3.  Inheritance:
    1.  [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
    2.  [`Element`](https://developer.mozilla.org/en-US/docs/Web/API/Element)
    3.  [`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node)
    4.  [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)
4.  Related pages for HTML DOM
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
