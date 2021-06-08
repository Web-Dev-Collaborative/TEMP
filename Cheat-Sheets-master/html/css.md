;

Basics
------

{: .-three-column}

### Selectors

    .class {
      font-weight: bold;
    }

{: .-setup}

<table><thead><tr class="header"><th>Selector</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>*</code></td><td>All elements</td></tr><tr class="even"><td><code>div</code></td><td>Element</td></tr><tr class="odd"><td><code>.class</code></td><td>Class</td></tr><tr class="even"><td><code>#id</code></td><td>ID</td></tr><tr class="odd"><td><code>[disabled]</code></td><td>Attribute</td></tr><tr class="even"><td><code>[role="dialog"]</code></td><td>Attribute</td></tr></tbody></table>

### Combinators

<table><thead><tr class="header"><th>Selector</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>.parent .child</code></td><td>Descendant</td></tr><tr class="even"><td><code>.parent &gt; .child</code></td><td>Direct descendant</td></tr><tr class="odd"><td><code>.child + .sibling</code></td><td>Adjacent sibling</td></tr><tr class="even"><td><code>.child ~ .sibling</code></td><td>Far sibling</td></tr><tr class="odd"><td><code>.class1.class2</code></td><td>Have both classes</td></tr></tbody></table>

### Attribute selectors

<table><thead><tr class="header"><th>Selector</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>[role="dialog"]</code></td><td><code>=</code> Exact</td></tr><tr class="even"><td><code>[class~="box"]</code></td><td><code>~=</code> Has word</td></tr><tr class="odd"><td><code>[class|="box"]</code></td><td><code>|=</code> Exact or prefix (eg, <code>value-</code>)</td></tr><tr class="even"><td><code>[href$=".doc"]</code></td><td><code>$=</code> Ends in</td></tr><tr class="odd"><td><code>[href^="/index"]</code></td><td><code>^=</code> Begins with</td></tr><tr class="even"><td><code>[class*="-is-"]</code></td><td><code>*=</code> Contains</td></tr></tbody></table>

### Pseudo-classes

<table><thead><tr class="header"><th>Selector</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>:target</code></td><td>eg, <code>h2#foo:target</code></td></tr><tr class="even"><td>—</td><td>—</td></tr><tr class="odd"><td><code>:disabled</code></td><td></td></tr><tr class="even"><td><code>:focus</code></td><td></td></tr><tr class="odd"><td><code>:active</code></td><td></td></tr><tr class="even"><td>—</td><td>—</td></tr><tr class="odd"><td><code>:nth-child(3)</code></td><td>3rd child</td></tr><tr class="even"><td><code>:nth-child(3n+2)</code></td><td>2nd child in groups of 3</td></tr><tr class="odd"><td><code>:nth-child(-n+4)</code></td><td></td></tr><tr class="even"><td>—</td><td>—</td></tr><tr class="odd"><td><code>:nth-last-child(2)</code></td><td></td></tr><tr class="even"><td><code>:nth-of-type(2)</code></td><td></td></tr><tr class="odd"><td>—</td><td>—</td></tr><tr class="even"><td><code>:checked</code></td><td>Checked inputs</td></tr><tr class="odd"><td><code>:disabled</code></td><td>Disabled elements</td></tr><tr class="even"><td><code>:default</code></td><td>Default element in a group</td></tr><tr class="odd"><td>—</td><td>—</td></tr><tr class="even"><td><code>:empty</code></td><td>Elements without children</td></tr></tbody></table>

### Pseudo-class variations

<table><thead><tr class="header"><th>Selector</th></tr></thead><tbody><tr class="odd"><td><code>:first-of-type</code></td></tr><tr class="even"><td><code>:last-of-type</code></td></tr><tr class="odd"><td><code>:nth-of-type(2)</code></td></tr><tr class="even"><td><code>:only-of-type</code></td></tr><tr class="odd"><td>—</td></tr><tr class="even"><td><code>:first-child</code></td></tr><tr class="odd"><td><code>:last-child</code></td></tr><tr class="even"><td><code>:nth-child(2)</code></td></tr><tr class="odd"><td><code>:only-child</code></td></tr></tbody></table>

{: .-left-align}

Fonts
-----

{: .-left-reference}

### Properties

<table><thead><tr class="header"><th>Property</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>font-family:</code></td><td><code>&lt;font&gt;, &lt;fontN&gt;</code></td></tr><tr class="even"><td><code>font-size:</code></td><td><code>&lt;size&gt;</code></td></tr><tr class="odd"><td><code>letter-spacing:</code></td><td><code>&lt;size&gt;</code></td></tr><tr class="even"><td><code>line-height:</code></td><td><code>&lt;number&gt;</code></td></tr><tr class="odd"><td>—</td><td>—</td></tr><tr class="even"><td><code>font-weight:</code></td><td><code>bold</code> <code>normal</code></td></tr><tr class="odd"><td><code>font-style:</code></td><td><code>italic</code> <code>normal</code></td></tr><tr class="even"><td><code>text-decoration:</code></td><td><code>underline</code> <code>none</code></td></tr><tr class="odd"><td>—</td><td>—</td></tr><tr class="even"><td><code>text-align:</code></td><td><code>left</code> <code>right</code> <code>center</code> <code>justify</code></td></tr><tr class="odd"><td><code>text-transform:</code></td><td><code>capitalize</code> <code>uppercase</code> <code>lowercase</code></td></tr></tbody></table>

{: .-key-values}

### Shorthand

{: .-prime}

<table><thead><tr class="header"><th></th><th>style</th><th>weight</th><th>size (required)</th><th></th><th>line-height</th><th>family</th></tr></thead><tbody><tr class="odd"><td><code>font:</code></td><td><code>italic</code></td><td><code>400</code></td><td><code>14px</code></td><td><code>/</code></td><td><code>1.5</code></td><td><code>sans-serif</code></td></tr><tr class="even"><td></td><td>style</td><td>weight</td><td>size (required)</td><td></td><td>line-height</td><td>family (required)</td></tr></tbody></table>

{: .-css-breakdown}

### Example

    font-family: Arial;
    font-size: 12pt;
    line-height: 1.5;
    letter-spacing: 0.02em;
    color: #aa3322;

### Case

    text-transform: capitalize; /* Hello */
    text-transform: uppercase; /* HELLO */
    text-transform: lowercase; /* hello */

Background
----------

{: .-left-reference}

### Properties

<table><thead><tr class="header"><th>Property</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>background:</code></td><td><em>(Shorthand)</em></td></tr><tr class="even"><td>—</td><td>—</td></tr><tr class="odd"><td><code>background-color:</code></td><td><code>&lt;color&gt;</code></td></tr><tr class="even"><td><code>background-image:</code></td><td><code>url(...)</code></td></tr><tr class="odd"><td><code>background-position:</code></td><td><code>left/center/right</code> <code>top/center/bottom</code></td></tr><tr class="even"><td><code>background-size:</code></td><td><code>cover</code> <code>X Y</code></td></tr><tr class="odd"><td><code>background-clip:</code></td><td><code>border-box</code> <code>padding-box</code> <code>content-box</code></td></tr><tr class="even"><td><code>background-repeat:</code></td><td><code>no-repeat</code> <code>repeat-x</code> <code>repeat-y</code></td></tr><tr class="odd"><td><code>background-attachment:</code></td><td><code>scroll</code> <code>fixed</code> <code>local</code></td></tr></tbody></table>

{: .-key-values}

### Shorthand

<table><thead><tr class="header"><th></th><th>color</th><th>image</th><th>positionX</th><th>positionY</th><th></th><th>size</th><th>repeat</th><th>attachment</th></tr></thead><tbody><tr class="odd"><td><code>background:</code></td><td><code>#ff0</code></td><td><code>url(bg.jpg)</code></td><td><code>left</code></td><td><code>top</code></td><td><code>/</code></td><td><code>100px</code> <code>auto</code></td><td><code>no-repeat</code></td><td><code>fixed;</code></td></tr><tr class="even"><td><code>background:</code></td><td><code>#abc</code></td><td><code>url(bg.png)</code></td><td><code>center</code></td><td><code>center</code></td><td><code>/</code></td><td><code>cover</code></td><td><code>repeat-x</code></td><td><code>local;</code></td></tr><tr class="odd"><td></td><td>color</td><td>image</td><td>positionX</td><td>positionY</td><td></td><td>size</td><td>repeat</td><td>attachment</td></tr></tbody></table>

{: .-css-breakdown}

### Multiple backgrounds

    background: linear-gradient(to bottom, rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)),
      url('background.jpg') center center / cover, #333;

Animation
---------

{: .-left-reference}

### Properties

<table><thead><tr class="header"><th>Property</th><th>Value</th></tr></thead><tbody><tr class="odd"><td><code>animation:</code></td><td><em>(shorthand)</em></td></tr><tr class="even"><td><code>animation-name:</code></td><td><code>&lt;name&gt;</code></td></tr><tr class="odd"><td><code>animation-duration:</code></td><td><code>&lt;time&gt;ms</code></td></tr><tr class="even"><td><code>animation-timing-function:</code></td><td><code>ease</code> <code>linear</code> <code>ease-in</code> <code>ease-out</code> <code>ease-in-out</code></td></tr><tr class="odd"><td><code>animation-delay:</code></td><td><code>&lt;time&gt;ms</code></td></tr><tr class="even"><td><code>animation-iteration-count:</code></td><td><code>infinite</code> <code>&lt;number&gt;</code></td></tr><tr class="odd"><td><code>animation-direction:</code></td><td><code>normal</code> <code>reverse</code> <code>alternate</code> <code>alternate-reverse</code></td></tr><tr class="even"><td><code>animation-fill-mode:</code></td><td><code>none</code> <code>forwards</code> <code>backwards</code> <code>both</code> <code>initial</code> <code>inherit</code></td></tr><tr class="odd"><td><code>animation-play-state:</code></td><td><code>normal</code> <code>reverse</code> <code>alternate</code> <code>alternate-reverse</code></td></tr></tbody></table>

{: .-key-values}

### Shorthand

<table><thead><tr class="header"><th></th><th>name</th><th>duration</th><th>timing-function</th><th>delay</th><th>count</th><th>direction</th><th>fill-mode</th><th>play-state</th></tr></thead><tbody><tr class="odd"><td><code>animation:</code></td><td><code>bounce</code></td><td><code>300ms</code></td><td><code>linear</code></td><td><code>100ms</code></td><td><code>infinite</code></td><td><code>alternate-reverse</code></td><td><code>both</code></td><td><code>reverse</code></td></tr><tr class="even"><td></td><td>name</td><td>duration</td><td>timing-function</td><td>delay</td><td>count</td><td>direction</td><td>fill-mode</td><td>play-state</td></tr></tbody></table>

{: .-css-breakdown}

### Example

    animation: bounce 300ms linear 0s infinite normal;
    animation: bounce 300ms linear infinite;
    animation: bounce 300ms linear infinite alternate-reverse;
    animation: bounce 300ms linear 2s infinite alternate-reverse forwards normal;

### Event

    .one('webkitAnimationEnd oanimationend msAnimationEnd animationend')
