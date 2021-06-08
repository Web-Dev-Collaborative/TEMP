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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/Node" class="breadcrumb-current-page"><span data-property="name">Node</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Properties](#properties)
-   [Methods](#methods)
-   [Examples](#examples)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)

Node
====

<span class="seoSummary">The [DOM](https://developer.mozilla.org/en-US/docs/Glossary/DOM) **`Node`** interface is an abstract base class upon which many other DOM API objects are based, thus letting those object types to be used similarly and often interchangeably.</span> As an abstract class, there is no such thing as a plain `Node` object. All objects that implement `Node` functionality are based on one of its subclasses. Most notable are [`Document`](https://developer.mozilla.org/en-US/docs/Web/API/Document), [`Element`](https://developer.mozilla.org/en-US/docs/Web/API/Element), and [`DocumentFragment`](https://developer.mozilla.org/en-US/docs/Web/API/DocumentFragment).

In addition, every kind of DOM node is represented by an interface based on `Node`. These include [`Attr`](https://developer.mozilla.org/en-US/docs/Web/API/Attr), [`CharacterData`](https://developer.mozilla.org/en-US/docs/Web/API/CharacterData) (which [`Text`](https://developer.mozilla.org/en-US/docs/Web/API/Text), [`Comment`](https://developer.mozilla.org/en-US/docs/Web/API/Comment), [`CDATASection`](https://developer.mozilla.org/en-US/docs/Web/API/CDATASection) and [`ProcessingInstruction`](https://developer.mozilla.org/en-US/docs/Web/API/ProcessingInstruction) are all based on), [`DocumentType`](https://developer.mozilla.org/en-US/docs/Web/API/DocumentType), <span class="page-not-created">`Notation`</span>, <span class="page-not-created">`Entity`</span>, and <span class="page-not-created">`EntityReference`</span>.

In some cases, a particular feature of the base `Node` interface may not apply to one of its child interfaces; in that case, the inheriting node may return `null` or throw an exception, depending on circumstances. For example, attempting to add children to a node type that cannot have children will throw an exception.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

*In addition to the properties below, `Node` inherits properties from its parent, [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)*.

[`Node.baseURI`](https://developer.mozilla.org/en-US/docs/Web/API/Node/baseURI)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) representing the base URL of the document containing the `Node`.

[`Node.childNodes`](https://developer.mozilla.org/en-US/docs/Web/API/Node/childNodes)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a live [`NodeList`](https://developer.mozilla.org/en-US/docs/Web/API/NodeList) containing all the children of this node (including elements, text and comments). [`NodeList`](https://developer.mozilla.org/en-US/docs/Web/API/NodeList) being live means that if the children of the `Node` change, the [`NodeList`](https://developer.mozilla.org/en-US/docs/Web/API/NodeList) object is automatically updated.

[`Node.firstChild`](https://developer.mozilla.org/en-US/docs/Web/API/Node/firstChild)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node) representing the first direct child node of the node, or `null` if the node has no child.

[`Node.isConnected`](https://developer.mozilla.org/en-US/docs/Web/API/Node/isConnected)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
A boolean indicating whether or not the Node is connected (directly or indirectly) to the context object, e.g. the [`Document`](https://developer.mozilla.org/en-US/docs/Web/API/Document) object in the case of the normal DOM, or the [`ShadowRoot`](https://developer.mozilla.org/en-US/docs/Web/API/ShadowRoot) in the case of a shadow DOM.

[`Node.lastChild`](https://developer.mozilla.org/en-US/docs/Web/API/Node/lastChild)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node) representing the last direct child node of the node, or `null` if the node has no child.

[`Node.nextSibling`](https://developer.mozilla.org/en-US/docs/Web/API/Node/nextSibling)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node) representing the next node in the tree, or `null` if there isn't such node.

[`Node.nodeName`](https://developer.mozilla.org/en-US/docs/Web/API/Node/nodeName)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) containing the name of the `Node`. The structure of the name will differ with the node type. E.g. An [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement) will contain the name of the corresponding tag, like `'audio'` for an [`HTMLAudioElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAudioElement), a [`Text`](https://developer.mozilla.org/en-US/docs/Web/API/Text) node will have the `'#text'` string, or a [`Document`](https://developer.mozilla.org/en-US/docs/Web/API/Document) node will have the `'#document'` string.

[`Node.nodeType`](https://developer.mozilla.org/en-US/docs/Web/API/Node/nodeType)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns an `unsigned short` representing the type of the node. Possible values are:

<table><thead><tr class="header"><th>Name</th><th>Value</th></tr></thead><tbody><tr class="odd"><td><code>ELEMENT_NODE</code></td><td><code>1</code></td></tr><tr class="even"><td><code>ATTRIBUTE_NODE</code> </td><td><code>2</code></td></tr><tr class="odd"><td><code>TEXT_NODE</code></td><td><code>3</code></td></tr><tr class="even"><td><code>CDATA_SECTION_NODE</code></td><td><code>4</code></td></tr><tr class="odd"><td><code>ENTITY_REFERENCE_NODE</code> </td><td><code>5</code></td></tr><tr class="even"><td><code>ENTITY_NODE</code> </td><td><code>6</code></td></tr><tr class="odd"><td><code>PROCESSING_INSTRUCTION_NODE</code></td><td><code>7</code></td></tr><tr class="even"><td><code>COMMENT_NODE</code></td><td><code>8</code></td></tr><tr class="odd"><td><code>DOCUMENT_NODE</code></td><td><code>9</code></td></tr><tr class="even"><td><code>DOCUMENT_TYPE_NODE</code></td><td><code>10</code></td></tr><tr class="odd"><td><code>DOCUMENT_FRAGMENT_NODE</code></td><td><code>11</code></td></tr><tr class="even"><td><code>NOTATION_NODE</code> </td><td><code>12</code></td></tr></tbody></table>

[`Node.nodeValue`](https://developer.mozilla.org/en-US/docs/Web/API/Node/nodeValue)  
Returns / Sets the value of the current node.

[`Node.ownerDocument`](https://developer.mozilla.org/en-US/docs/Web/API/Node/ownerDocument)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the [`Document`](https://developer.mozilla.org/en-US/docs/Web/API/Document) that this node belongs to. If the node is itself a document, returns `null`.

[`Node.parentNode`](https://developer.mozilla.org/en-US/docs/Web/API/Node/parentNode)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node) that is the parent of this node. If there is no such node, like if this node is the top of the tree or if doesn't participate in a tree, this property returns `null`.

[`Node.parentElement`](https://developer.mozilla.org/en-US/docs/Web/API/Node/parentElement)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns an [`Element`](https://developer.mozilla.org/en-US/docs/Web/API/Element) that is the parent of this node. If the node has no parent, or if that parent is not an [`Element`](https://developer.mozilla.org/en-US/docs/Web/API/Element), this property returns `null`.

[`Node.previousSibling`](https://developer.mozilla.org/en-US/docs/Web/API/Node/previousSibling)<span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node) representing the previous node in the tree, or `null` if there isn't such node.

[`Node.textContent`](https://developer.mozilla.org/en-US/docs/Web/API/Node/textContent)  
Returns / Sets the textual content of an element and all its descendants.

[Methods](#methods "Permalink to Methods")
------------------------------------------

*In addition to the properties below, `Node` inherits methods from its parent, [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget).*

[`Node.appendChild(childNode)`](https://developer.mozilla.org/en-US/docs/Web/API/Node/appendChild "Node.appendChild(<var>childNode</var>)")  
Adds the specified `childNode` argument as the last child to the current node.  
If the argument referenced an existing node on the DOM tree, the node will be detached from its current position and attached at the new position.

[`Node.cloneNode()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/cloneNode)  
Clone a [`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node), and optionally, all of its contents. By default, it clones the content of the node.

[`Node.compareDocumentPosition()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/compareDocumentPosition)  
Compares the position of the current node against another node in any other document.

[`Node.contains()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/contains)  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) value indicating whether or not a node is a descendant of the calling node.

<span class="page-not-created">`Node.getBoxQuads()`</span>   
Returns a list of the node's CSS boxes relative to another node.

[`Node.getRootNode()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/getRootNode)  
Returns the context object's root which optionally includes the shadow root if it is available. 

[`Node.hasChildNodes()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/hasChildNodes)  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether or not the element has any child nodes.

[`Node.insertBefore()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/insertBefore)  
Inserts a [`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node) before the reference node as a child of a specified parent node.

[`Node.isDefaultNamespace()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/isDefaultNamespace)  
Accepts a namespace URI as an argument and returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) with a value of `true` if the namespace is the default namespace on the given node or `false` if not.

[`Node.isEqualNode()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/isEqualNode)  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) which indicates whether or not two nodes are of the same type and all their defining data points match.

[`Node.isSameNode()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/isSameNode)  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) value indicating whether or not the two nodes are the same (that is, they reference the same object).

[`Node.lookupPrefix()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/lookupPrefix)  
Returns a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) containing the prefix for a given namespace URI, if present, and `null` if not. When multiple prefixes are possible, the result is implementation-dependent.

[`Node.lookupNamespaceURI()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/lookupNamespaceURI)  
Accepts a prefix and returns the namespace URI associated with it on the given node if found (and `null` if not). Supplying `null` for the prefix will return the default namespace.

[`Node.normalize()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/normalize)  
Clean up all the text nodes under this element (merge adjacent, remove empty).

[`Node.removeChild()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/removeChild)  
Removes a child node from the current element, which must be a child of the current node.

[`Node.replaceChild()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/replaceChild)  
Replaces one child [`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node) of the current one with the second one given in parameter.

### [Obsolete methods](#obsolete_methods "Permalink to Obsolete methods")

[`Node.getUserData()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/getUserData)    
Allows a user to get some [`DOMUserData`](https://developer.mozilla.org/en-US/docs/Web/API/DOMUserData) from the node.

<span class="page-not-created">`Node.hasAttributes()`</span>    
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating if the element has any attributes, or not.

[`Node.isSupported()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/isSupported)    
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) flag containing the result of a test whether the DOM implementation implements a specific feature and this feature is supported by the specific node.

[`Node.setUserData()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/setUserData)    
Allows a user to attach, or remove, [`DOMUserData`](https://developer.mozilla.org/en-US/docs/Web/API/DOMUserData) to the node.

[Examples](#examples "Permalink to Examples")
---------------------------------------------

### [Remove all children nested within a node](#remove_all_children_nested_within_a_node "Permalink to Remove all children nested within a node
")

    function removeAllChildren(element) {
      while (element.firstChild) {
        element.removeChild(element.firstChild)
      }
    }

#### Sample usage

    /* Note: or use document.body.textContent = "" */
    removeAllChildren(document.body)

### [Recurse through child nodes](#recurse_through_child_nodes "Permalink to Recurse through child nodes")

The following function recursively calls a callback function for each node contained by a root node (including the root itself):

    function eachNode(rootNode, callback) {
        if (!callback) {
            const nodes = []
            eachNode(rootNode, function(node) {
                nodes.push(node)
            })
            return nodes
        }

        if (false === callback(rootNode)) {
            return false
        }

        if (rootNode.hasChildNodes()) {
            const nodes = rootNode.childNodes
            for (let i = 0, l = nodes.length; i < l; ++i) {
                if (false === eachNode(nodes[i], callback)) {
                    return
                }
            }
        }
    }

#### Syntax

    eachNode(rootNode, callback)

#### Description

Recursively calls a function for each descendant node of `rootNode` (including the root itself).

If `callback` is omitted, the function returns an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) instead, which contains `rootNode` and all nodes contained within.

If `callback` is provided, and it returns [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) `false` when called, the current recursion level is aborted, and the function resumes execution at the last parent's level. This can be used to abort loops once a node has been found (such as searching for a text node which contains a certain string).

#### Parameters

`rootNode`  
The `Node` object whose descendants will be recursed through.

`callback` <span class="badge inline optional">Optional</span>  
An optional callback [function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function) that receives a `Node` as its only argument. If omitted, `eachNode` returns an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of every node contained within `rootNode` (including the root itself).

#### Sample usage

The following example prints the [`textContent`](https://developer.mozilla.org/en-US/docs/Web/API/Node/textContent) properties of each `<span>` tag in a `<div>` element named `"box"`:

    <div id="box">
      <span>Foo</span>
      <span>Bar</span>
      <span>Baz</span>
    </div>

    const box = document.getElementById("box")
    eachNode(box, function(node) {
      if (null != node.textContent) {
        console.log(node.textContent)
      }
    })

The above will result in the following strings printing to the user's console:

    "\n\t", "Foo", "\n\t", "Bar", "\n\t", "Baz"

**Note:** Whitespace forms part of a [`Text`](https://developer.mozilla.org/en-US/docs/Web/API/Text) node, meaning indentation and newlines form separate `Text` between the `Element` nodes.

#### Realistic usage

The following demonstrates a real-world use of the `eachNode()` function: searching for text on a web-page.

We use a wrapper function named `grep` to do the searching:

    function grep(parentNode, pattern) {
        const matches = []
        let endScan = false

        eachNode(parentNode, function(node){
            if (endScan) {
                return false
            }

            // Ignore anything which isn't a text node
            if (node.nodeType !== Node.TEXT_NODE) {
                return
            }

            if (typeof pattern === "string") {
                if (-1 !== node.textContent.indexOf(pattern)) {
                    matches.push(node)
                }
            }
            else if (pattern.test(node.textContent)) {
                if (!pattern.global) {
                    endScan = true
                    matches = node
                }
                else {
                    matches.push(node)
                }
            }
        })

        return matches
    }

For example, to find [`Text`](https://developer.mozilla.org/en-US/docs/Web/API/Text) nodes that contain typos:

    const typos = ["teh", "adn", "btu", "adress", "youre", "msitakes"]
    const pattern = new RegExp("\\b(" + typos.join("|") + ")\\b", "gi")
    const mistakes = grep(document.body, pattern)
    console.log(mistakes)

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#interface-node" class="external">DOM<br />
<span class="small">The definition of 'Node' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Added the following methods: <code>getRootNode()</code></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/dom/#interface-node" class="external">DOM4<br />
<span class="small">The definition of 'Node' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Removed the following properties: <code>attributes</code>, <code>namespaceURI</code>, <code>prefix</code>, and <code>localName</code>.<br />
Removed the following methods: <code>isSupported()</code>, <code>hasAttributes()</code>, <code>getFeature()</code>, <code>setUserData()</code>, and <code>getUserData()</code>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-3-Core/core.html#ID-1950641247" class="external">Document Object Model (DOM) Level 3 Core Specification<br />
<span class="small">The definition of 'Node' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>The methods <code>insertBefore()</code>, <code>replaceChild()</code>, <code>removeChild()</code>, and <code>appendChild()</code> returns one more kind of error (<code>NOT_SUPPORTED_ERR</code>) if called on a <a href="https://developer.mozilla.org/en-US/docs/Web/API/Document"><code>Document</code></a>.<br />
The <code>normalize()</code> method has been modified so that <a href="https://developer.mozilla.org/en-US/docs/Web/API/Text"><code>Text</code></a> node can also be normalized if the proper <span class="page-not-created"><code>DOMConfiguration</code></span> flag is set.<br />
Added the following methods: <code>compareDocumentPosition()</code>, <code>isSameNode()</code>, <code>lookupPrefix()</code>, <code>isDefaultNamespace()</code>, <code>lookupNamespaceURI()</code>, <code>isEqualNode()</code>, <code>getFeature()</code>, <code>setUserData()</code>, and <code>getUserData().</code><br />
Added the following properties: <code>baseURI</code> and <code>textContent</code>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Core/core.html#ID-1950641247" class="external">Document Object Model (DOM) Level 2 Core Specification<br />
<span class="small">The definition of 'Node' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>The <code>ownerDocument</code> property was slightly modified so that <a href="https://developer.mozilla.org/en-US/docs/Web/API/DocumentFragment"><code>DocumentFragment</code></a> also returns <code>null</code>.<br />
Added the following properties: <code>namespaceURI</code>, <code>prefix</code>, and <code>localName</code>.<br />
Added the following methods: <code>normalize()</code>, <code>isSupported()</code> and <code>hasAttributes()</code>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-core.html#ID-1950641247" class="external">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'Node' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/node/index.html "Folder: en-us/web/api/node (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FNode%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fnode%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FNode%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fnode%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F9b648e559239b3e682abfcb15845a954d420b207%0A*+Document+last+modified%3A+2021-05-31T17%3A00%3A38.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22Node%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/Node/contributors.txt)

Change your languageSelect your preferred language English (US)DeutschEspañolFrançais日本語한국어Português (do Brasil)Русский中文 (简体)正體中文 (繁體)

Change language

#### Related Topics

1.  **[Document Object Model](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model)**
2.  **[`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node)**
3.  Properties
    1.  [`baseURI`](https://developer.mozilla.org/en-US/docs/Web/API/Node/baseURI)
    2.  [`childNodes`](https://developer.mozilla.org/en-US/docs/Web/API/Node/childNodes)
    3.  [`firstChild`](https://developer.mozilla.org/en-US/docs/Web/API/Node/firstChild)
    4.  [`isConnected`](https://developer.mozilla.org/en-US/docs/Web/API/Node/isConnected)
    5.  [`lastChild`](https://developer.mozilla.org/en-US/docs/Web/API/Node/lastChild)
    6.  [`nextSibling`](https://developer.mozilla.org/en-US/docs/Web/API/Node/nextSibling)
    7.  [`nodeName`](https://developer.mozilla.org/en-US/docs/Web/API/Node/nodeName)
    8.  [`nodeType`](https://developer.mozilla.org/en-US/docs/Web/API/Node/nodeType)
    9.  [`nodeValue`](https://developer.mozilla.org/en-US/docs/Web/API/Node/nodeValue)
    10. [`ownerDocument`](https://developer.mozilla.org/en-US/docs/Web/API/Node/ownerDocument)
    11. [`parentElement`](https://developer.mozilla.org/en-US/docs/Web/API/Node/parentElement)
    12. [`parentNode`](https://developer.mozilla.org/en-US/docs/Web/API/Node/parentNode)
    13. [`previousSibling`](https://developer.mozilla.org/en-US/docs/Web/API/Node/previousSibling)
    14. [`textContent`](https://developer.mozilla.org/en-US/docs/Web/API/Node/textContent)
4.  Methods
    1.  [`appendChild()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/appendChild)
    2.  [`cloneNode()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/cloneNode)
    3.  [`compareDocumentPosition()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/compareDocumentPosition)
    4.  [`contains()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/contains)
    5.  [`getRootNode()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/getRootNode)
    6.  [`getUserData()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/getUserData)
    7.  [`hasChildNodes()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/hasChildNodes)
    8.  [`insertBefore()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/insertBefore)
    9.  [`isDefaultNamespace()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/isDefaultNamespace)
    10. [`isEqualNode()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/isEqualNode)
    11. [`isSameNode()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/isSameNode)
    12. [`isSupported()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/isSupported)
    13. [`lookupNamespaceURI()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/lookupNamespaceURI)
    14. [`lookupPrefix()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/lookupPrefix)
    15. [`normalize()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/normalize)
    16. [`removeChild()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/removeChild)
    17. [`replaceChild()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/replaceChild)
    18. [`setUserData()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/setUserData)
5.  Inheritance:
    1.  [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)
6.  Related pages for DOM
    1.  [`AbortController`](https://developer.mozilla.org/en-US/docs/Web/API/AbortController)
    2.  [`AbortSignal`](https://developer.mozilla.org/en-US/docs/Web/API/AbortSignal)
    3.  [`AbstractRange`](https://developer.mozilla.org/en-US/docs/Web/API/AbstractRange)
    4.  [`Attr`](https://developer.mozilla.org/en-US/docs/Web/API/Attr)
    5.  [`ByteString`](https://developer.mozilla.org/en-US/docs/Web/API/ByteString)
    6.  [`CDATASection`](https://developer.mozilla.org/en-US/docs/Web/API/CDATASection)
    7.  [`CSSPrimitiveValue`](https://developer.mozilla.org/en-US/docs/Web/API/CSSPrimitiveValue)
    8.  [`CSSValue`](https://developer.mozilla.org/en-US/docs/Web/API/CSSValue)
    9.  [`CSSValueList`](https://developer.mozilla.org/en-US/docs/Web/API/CSSValueList)
    10. [`CharacterData`](https://developer.mozilla.org/en-US/docs/Web/API/CharacterData)
    11. [`ChildNode`](https://developer.mozilla.org/en-US/docs/Web/API/ChildNode)
    12. [`Comment`](https://developer.mozilla.org/en-US/docs/Web/API/Comment)
    13. [`CustomEvent`](https://developer.mozilla.org/en-US/docs/Web/API/CustomEvent)
    14. [`DOMConfiguration`](https://developer.mozilla.org/en-US/docs/Web/API/DOMConfiguration)
    15. [`DOMError`](https://developer.mozilla.org/en-US/docs/Web/API/DOMError)
    16. [`DOMErrorHandler`](https://developer.mozilla.org/en-US/docs/Web/API/DOMErrorHandler)
    17. [`DOMException`](https://developer.mozilla.org/en-US/docs/Web/API/DOMException)
    18. [`DOMImplementation`](https://developer.mozilla.org/en-US/docs/Web/API/DOMImplementation)
    19. [`DOMImplementationList`](https://developer.mozilla.org/en-US/docs/Web/API/DOMImplementationList)
    20. [`DOMImplementationRegistry`](https://developer.mozilla.org/en-US/docs/Web/API/DOMImplementationRegistry)
    21. [`DOMImplementationSource`](https://developer.mozilla.org/en-US/docs/Web/API/DOMImplementationSource)
    22. [`DOMLocator`](https://developer.mozilla.org/en-US/docs/Web/API/DOMLocator)
    23. [`DOMObject`](https://developer.mozilla.org/en-US/docs/Web/API/DOMObject)
    24. [`DOMParser`](https://developer.mozilla.org/en-US/docs/Web/API/DOMParser)
    25. [`DOMPoint`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPoint)
    26. [`DOMPointInit`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPointInit)
    27. [`DOMPointReadOnly`](https://developer.mozilla.org/en-US/docs/Web/API/DOMPointReadOnly)
    28. [`DOMRect`](https://developer.mozilla.org/en-US/docs/Web/API/DOMRect)
    29. [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString)
    30. [`DOMTimeStamp`](https://developer.mozilla.org/en-US/docs/Web/API/DOMTimeStamp)
    31. [`DOMTokenList`](https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList)
    32. [`DOMUserData`](https://developer.mozilla.org/en-US/docs/Web/API/DOMUserData)
    33. [`Document`](https://developer.mozilla.org/en-US/docs/Web/API/Document)
    34. [`DocumentFragment`](https://developer.mozilla.org/en-US/docs/Web/API/DocumentFragment)
    35. [`DocumentType`](https://developer.mozilla.org/en-US/docs/Web/API/DocumentType)
    36. [`Element`](https://developer.mozilla.org/en-US/docs/Web/API/Element)
    37. [`ElementTraversal`](https://developer.mozilla.org/en-US/docs/Web/API/ElementTraversal)
    38. [`Entity`](https://developer.mozilla.org/en-US/docs/Web/API/Entity)
    39. [`EntityReference`](https://developer.mozilla.org/en-US/docs/Web/API/EntityReference)
    40. [`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event)
    41. [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)
    42. [`HTMLCollection`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCollection)
    43. [`MutationObserver`](https://developer.mozilla.org/en-US/docs/Web/API/MutationObserver)
    44. [`NodeFilter`](https://developer.mozilla.org/en-US/docs/Web/API/NodeFilter)
    45. [`NodeIterator`](https://developer.mozilla.org/en-US/docs/Web/API/NodeIterator)
    46. [`NodeList`](https://developer.mozilla.org/en-US/docs/Web/API/NodeList)
    47. [`ProcessingInstruction`](https://developer.mozilla.org/en-US/docs/Web/API/ProcessingInstruction)
    48. [`PromiseResolver`](https://developer.mozilla.org/en-US/docs/Web/API/PromiseResolver)
    49. [`Range`](https://developer.mozilla.org/en-US/docs/Web/API/Range)
    50. [`StaticRange`](https://developer.mozilla.org/en-US/docs/Web/API/StaticRange)
    51. [`Text`](https://developer.mozilla.org/en-US/docs/Web/API/Text)
    52. [`TextDecoder`](https://developer.mozilla.org/en-US/docs/Web/API/TextDecoder)
    53. [`TextEncoder`](https://developer.mozilla.org/en-US/docs/Web/API/TextEncoder)
    54. [`TimeRanges`](https://developer.mozilla.org/en-US/docs/Web/API/TimeRanges)
    55. [`TreeWalker`](https://developer.mozilla.org/en-US/docs/Web/API/TreeWalker)
    56. [`TypeInfo`](https://developer.mozilla.org/en-US/docs/Web/API/TypeInfo)
    57. [`USVString`](https://developer.mozilla.org/en-US/docs/Web/API/USVString)
    58. [`UserDataHandler`](https://developer.mozilla.org/en-US/docs/Web/API/UserDataHandler)
    59. [`XMLDocument`](https://developer.mozilla.org/en-US/docs/Web/API/XMLDocument)

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
