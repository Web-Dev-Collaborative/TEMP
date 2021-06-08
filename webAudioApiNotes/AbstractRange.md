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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/AbstractRange" class="breadcrumb-current-page"><span data-property="name">AbstractRange</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Properties](#properties)
-   [Methods](#methods)
-   [Usage notes](#usage_notes)
-   [Example](#example)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)

AbstractRange
=============

<span class="seoSummary">The **`AbstractRange`** abstract interface is the base class upon which all [DOM](https://developer.mozilla.org/en-US/docs/Glossary/DOM) range types are defined. A **range** is an object that indicates the start and end points of a section of content within the document.</span>

As an abstract interface, you will not directly instantiate an object of type `AbstractRange`. Instead, you will use the [`Range`](https://developer.mozilla.org/en-US/docs/Web/API/Range) or [`StaticRange`](https://developer.mozilla.org/en-US/docs/Web/API/StaticRange) interfaces. To understand the difference between those two interfaces, and how to choose which is appropriate for your needs.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

 [`collapsed`](https://developer.mozilla.org/en-US/docs/Web/API/AbstractRange/collapsed "collapsed") <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
A Boolean value which is `true` if the range is **collapsed**. A collapsed range is one whose start position and end position are the same, resulting in a zero-character-long range.

 [`endContainer`](https://developer.mozilla.org/en-US/docs/Web/API/AbstractRange/endContainer "endContainer") <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
The DOM [`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node) in which the end of the range, as specified by the `endOffset` property, is located.

 [`endOffset`](https://developer.mozilla.org/en-US/docs/Web/API/AbstractRange/endOffset "endOffset") <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
An integer value indicating the offset, in characters, from the beginning of the node's contents to the beginning of the range represented by the range object. This value must be less than the length of the `endContainer` node.

 [`startContainer`](https://developer.mozilla.org/en-US/docs/Web/API/AbstractRange/startContainer "startContainer") <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
The DOM [`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node) in which the beginning of the range, as specified by the `startOffset` property, is located.

 [`startOffset`](https://developer.mozilla.org/en-US/docs/Web/API/AbstractRange/startOffset "startOffset") <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
An integer value indicating the offset, in characters, from the beginning of the node's contents to the last character of the contents referred to  by the range object. This value must be less than the length of the node indicated in `startContainer`.

[Methods](#methods "Permalink to Methods")
------------------------------------------

*The `AbstractRange` interface offers no methods.*

[Usage notes](#usage_notes "Permalink to Usage notes")
------------------------------------------------------

### [Range types](#range_types "Permalink to Range types")

All ranges of content within a [`document`](https://developer.mozilla.org/en-US/docs/Web/API/Document "document") are described using instances of interfaces based on `AbstractRange`. There are two such interfaces:

 [`Range`](https://developer.mozilla.org/en-US/docs/Web/API/Range)   
The `Range` interface has been around for a long time and has only recently been redefined to be based upon `AbstractRange` as the need arose to define other forms of range data. `Range` provides methods that allow you to alter the range's endpoints, as well as methods to compare ranges, detect intersections beween ranges, and so forth.

 [`StaticRange`](https://developer.mozilla.org/en-US/docs/Web/API/StaticRange)   
A `StaticRange` is a basic range which cannot be changed once it's been created. Specifically, as the node tree mutates and changes, the range does not. This is useful when you need to specify a range that will only be used once, since it avoids the performance and resource impact of the more complex [`Range`](https://developer.mozilla.org/en-US/docs/Web/API/Range) interface.

### [Contents of elements](#contents_of_elements "Permalink to Contents of elements")

When trying to access the contents of an element, keep in mind that the element itself is a node, but so is any text inside it. In order to set a range endpoint within the text of an element, be sure to find the text node inside the element:

    let startElem = document.querySelector("p");
    let endElem = startElem.querySelector("span");
    let range = document.createRange();

    range.setStart(startElem, 0);
    range.setEnd(endElem, endElem.childNodes[0].length/2);
    let contents = range.cloneContents();

    document.body.appendChild(contents);

This example creates a new range, `rng`, and sets its starting point to the third child node of the first element whose class is `elementclass`. The end point is set to be the middle of the first child of the span, and then the range is used to copy the contents of the range.

### [Ranges and the hierarchy of the DOM](#ranges_and_the_hierarchy_of_the_dom "Permalink to Ranges and the hierarchy of the DOM")

In order to define a range of characters within a document in a way that is able to span across zero or more node boundaries, and which is as resilient as possible to changes to the DOM, you can't specify the offset to the first and last characters in the [HTML](https://developer.mozilla.org/en-US/docs/Glossary/HTML). There are a few good reasons for that.

First, after your page is loaded, the browser isn't thinking in terms of HTML. Once it's been loaded, the page is a tree of DOM [`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node) objects, so you need to specify the beginning and ending locations of a range in terms of nodes and positions within nodes.

Second, in order to support the mutability of the DOM tree as much as possible, you need a way to represent positions relative to nodes in the tree, rather than global positions within the entire document. By defining points within the document as offsets within a given node, those positions remain consistent with the content even as nodes are added to, removed from, or moved around within the DOM tree—within reason. There are fairly obvious limitations (such as if a node is moved to be after the endpoint of a range, or if the content of a node is heavily altered), but it's far better than nothing.

Third, using node-relative positions to define the start and end positions will generally be easier to make perform well. Rather than having to negotiate the DOM figuring out what your global offset refers to, the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) (browser) can instead go directly to the node indicated by the starting position and start from there, working its way forward until it reaches the given offset into the ending node.

To illustrate this, consider the HTML below:

    <div class="container">
      <div class="header">
        <img src="" class="sitelogo">
        <h1>The Ultimate Website</h1>
      </div>
      <article>
        <section class="entry" id="entry1">
          <h2>Section 1: An interesting thing...</h2>
          <p>A <em>very</em> interesting thing happened on the way to the forum...</p>
          <aside class="callout">
            <h2>Aside</h2>
            <p>An interesting aside to share with you...</p>
          </aside>
        </section>
      </article>
      <pre id="log"></pre>
    </div>

After loading the HTML and constructing the DOM representation of the document, the resulting DOM tree looks like this:

<a href="https://mdn.mozillademos.org/files/16886/SimpleDOM.svg" class="external"><img src="https://developer.mozilla.org/en-US/docs/Web/API/AbstractRange/simpledom.svg" alt="Diagram of the DOM for a simple web page" width="1080" height="1152" /></a>

In this diagram, the nodes representing HTML elements are shown in green. Eah row beneath them shows the next layer of depth into the DOM tree. Blue nodes are text nodes, containing the text that gets shown onscreen. Each element's contents are linked below it in the tree, potentially spawning a series of branches below as elements include other elements and text nodes.

If you want to create a range that incorporates the contents of the [`<p>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p) element whose contents are `"A <em>very</em> interesting thing happened on                   the way to the forum..."`, you can do so like this:

    let pRange = document.createRange();
    pRange.selectNodeContents(document.querySelector("#entry1 p"));

Since we wish to select the entire contents of the `<p>` element, including its descendants, this works perfectly.

If we wish to instead copy the text "An interesting thing..." from the [`<section>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/section)'s heading (an [`<h2>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements) element) through the end of the letters "ve" in the [`<em>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/em) within the paragraph below it, the following code would work:

    let r = document.createRange();
    let startNode = document.querySelector("section h2").childNodes[0];
    r.setStart(startNode, 11);

    let endNode = document.querySelector("#entry1 p em").childNodes[0];
    r.setEnd(endNode, 2);

    let fragment = r.cloneContents();

Here an interesting problem arises—we are capturing content from multiple nodes located at different levels of the DOM hierarchy, and then only part of one of them. What should the result look like?

As it turns out, the DOM specification fortunately addresses this exact issue. For example, in this case, we're calling [`cloneContents()`](https://developer.mozilla.org/en-US/docs/Web/API/Range/cloneContents "cloneContents()") on the range to create a new [`DocumentFragment`](https://developer.mozilla.org/en-US/docs/Web/API/DocumentFragment) object providing a DOM subtree which replicates the contents of the specfied range. To do this, `cloneContents()` constructs all the nodes needed to preserve the structure of the indicated range, but no more than necessary.

In this example, the start of the specified range is found within the text node below the section's heading, which means that the new `DocumentFragment` will need to contain an [`<h2>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements) and, below it, a text node.

The range's end is located below the <span class="page-not-created">`p`</span> element, so that will be needed within the new fragment. So will the text node containing the word "A", since that's included in the range. Finally, an `<em>` and a text node below it will be added below the `<p>` as well.

The contents of the text nodes are then determined by the offsets into those text nodes given when calling [`setStart()`](https://developer.mozilla.org/en-US/docs/Web/API/Range/setStart "setStart()") and [`setEnd()`](https://developer.mozilla.org/en-US/docs/Web/API/Range/setEnd "setEnd()"). Given the offset of 11 into the heading's text, that node will contain "An interesting thing...". Similarly, the last text node will contain "ve", given the request for the first two characters of the ending node.

The resulting document fragment looks like this:

<img src="https://developer.mozilla.org/en-US/docs/Web/API/AbstractRange/dom-fragment.svg" alt="A DocumentFragment representing the cloned content" width="463" height="319" />

Notice especially that the contents of this fragment are all *below* the shared common parent of the topmost nodes within it. The parent `<section>` is not needed to replicate the cloned content, so it is isn't included.

[Example](#example "Permalink to Example")
------------------------------------------

Consider this simple HTML fragment of HTML.

    <p><strong>This</strong> is a paragraph.</p>

Imagine using a [`Range`](https://developer.mozilla.org/en-US/docs/Web/API/Range) to extract the word "paragraph" from this. The code to do that looks like the following:

    let paraNode = document.querySelector("p");
    let paraTextNode = paraNode.childNodes[1];

    let range = document.createRange();
    range.setStart(paraTextNode, 6);
    range.setEnd(paraTextNode, paraTextNode.length-1);

    let fragment = range.cloneContents();
    document.body.appendChild(fragment);

First we get references to the paragraph node itelf as well as to the *second* child node within the paragraph. The first child is the [`<strong>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/strong) element. The second child is the text node " is a paragraph.".

With the text node reference in hand, we create a new `Range` object by calling [`createRange()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createRange "createRange()") on the `Document` itself. We set the starting position of the range to the sixth character of the text node's string, and the end position to the length of the text node's string minus one. This sets the range to encompass the word "paragraph".

We then finish up by calling [`cloneContents()`](https://developer.mozilla.org/en-US/docs/Web/API/Range/cloneContents "cloneContents()") on the `Range` to create a new [`DocumentFragment`](https://developer.mozilla.org/en-US/docs/Web/API/DocumentFragment) object which contains the portion of the document encompassed by the range. After that, we use [`appendChild()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/appendChild "appendChild()") to add that fragment at the end of the document's body, as obtained from [`document.body`](https://developer.mozilla.org/en-US/docs/Web/API/Document/body).

The result looks like this:

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#abstractrange" class="external">DOM<br />
<span class="small">The definition of 'AbstractRange' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/abstractrange/index.html "Folder: en-us/web/api/abstractrange (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAbstractRange%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fabstractrange%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAbstractRange%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fabstractrange%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fc141b2c35a21ca911a3dc050de0d77695873dba5%0A*+Document+last+modified%3A+2021-05-29T02%3A55%3A10.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22AbstractRange%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 29, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/AbstractRange/contributors.txt)

Change your language Select your preferred language English (US) 한국어

Change language

#### Related Topics

1.  **[`AbstractRange`](https://developer.mozilla.org/en-US/docs/Web/API/AbstractRange)**
2.  Properties
    1.  [`collapsed`](https://developer.mozilla.org/en-US/docs/Web/API/AbstractRange/collapsed)
    2.  [`endContainer`](https://developer.mozilla.org/en-US/docs/Web/API/AbstractRange/endContainer)
    3.  [`endOffset`](https://developer.mozilla.org/en-US/docs/Web/API/AbstractRange/endOffset)
    4.  [`startContainer`](https://developer.mozilla.org/en-US/docs/Web/API/AbstractRange/startContainer)
    5.  [`startOffset`](https://developer.mozilla.org/en-US/docs/Web/API/AbstractRange/startOffset)

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
