;

### Creating ranges

See <a href="http://devdocs.io/dom/document/createrange" class="uri">http://devdocs.io/dom/document/createrange</a>

    var range = document.createRange()

Methods
-------

See <a href="http://devdocs.io/dom/range" class="uri">http://devdocs.io/dom/range</a>

    range
      .setStart(startNode, startOffset)
      .setEnd(endNode, endOffset)

      .setStartBefore(node)
      .setStartAfter(node)
      .setEndBefore(node)
      .setEndAfter(node)

      .selectNode(node)
      .selectNodeContents(node)

### Collapsing

    range
      .collapse()     // to end (a single point)
      .collapse(true) // to start (a single point)
      .collapsed      // true | false

### Operations

    range
      .cloneContents()   // copy => DocumentFragment
      .extractContents() // cut  => DocumentFragment
      .deleteContents()  // delete

      .insertNode(node)

### Etc

    range
      .toString()

### Read-only attributes

    range
      .collapsed         // true/false
      .startContainer    // Node
      .startOffset
      .endContainer      // Node
      .endOffset
      .commonAncestorContainer // closest of start and end containers
