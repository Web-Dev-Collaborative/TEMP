;

Selection
---------

See <a href="http://devdocs.io/dom/selection" class="uri">http://devdocs.io/dom/selection</a>

    var selection = document.getSelection()

Methods
-------

    selection
      .removeAllRanges()   // deselects
      .addRange(range)     // sets a selection
      .removeRange(range)  // remove a range

    selection
      .rangeCount          // ranges
      .getRangeAt(0)       // get the 0th range

### Collapsing

    selection
      .collapse(parent, offset)
      .collapseToEnd()
      .collapseToStart()
      .isCollapsed

    selection
      .containsNode(node)

### Deleting

    selection
      .deleteFromDocument()

### Events

    document.addEventListener('selectionchange', () => {})
