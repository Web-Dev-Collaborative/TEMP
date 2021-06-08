;

Intro
-----

Variants
--------

{: .-three-column}

### H2 sections

`-one-column` | |  
`-two-column` | *(default)*|  
`-three-column` | |  
`-left-reference` | 3 columns  
*(short first column)*|  
`-no-hide` | Don’t hide H2 |

See: [H2 sections](#two-columns)

### H3 sections

`-prime` | Highlight |

See: [H3 sections](#h3-sections-1)

### Tables

`-bold-first` | Bold first column |  
`-headers` | Show headers |  
`-left-align` | Don’t right align last column |  
`-mute-em` | Lower opacity for italics |  
`-no-wrap` | Don’t wrap text |  
`-shortcuts` | Shortcut keys |

See: [Tables](#tables-1)

### Code

`-box-chars` | Less line height  
*for box drawing chars*|  
`-setup` | Gray background |  
`-wrap` | Enables line-wrapping |

See: [Code](#code-1)

### Paragraphs

`-setup` | Gray background |  
`-crosslink` | Has arrow on the link |

{: .-gray}

See: [Paragraphs](#paragraphs-1)

### Lists

`-also-see` | Lighter background |  
`-four-column` | |  
`-six-column` | |

See: [Lists](#lists-1)

### Adding variants

{: .-prime}

    ## Section
    {: .-two-column}

Devhints uses Kramdown, and supports adding classes via Kramdown’s syntax.

H3 sections
-----------

{: .-three-column}

### Supported

Each section can have the following children:

#### White

-   `pre`
-   `ul`
-   `table`

#### Gray

-   `p`
-   `h4`

### Prime section

{: .-prime}

This is a section with `{: .-prime}`. Notice the fancy highlight! Great for “getting started” kind of snippets.

### H3 section

Every box is an H3 section. The box will encompass everything inside the body of the H3.

This is a basic section with paragraphs in it.

Code
----

{: .-three-column}

### Basic code

    here.is(() => {
      some.code()
    })

    here.is.some.more()

Code blocks can be placed one after the other.

See: [Cheatsheets](/)

### Code with headings

#### index.js

{: .-file}

    here.is(() => {
      some.code()
    })

#### other.js

{: .-file}

    here.is.some.more()

Code blocks can have headings.

### Highlighted lines

    app.start(() => {
      const port = app.server.port
      console.log(`Started at ${port}`)
    })

{: data-line=“3”}

Add `{: data-line="3"}` to add line highlights.

### Multiple highlights

    app.start(() => {
      const port = app.server.port
      console.log(`Started at ${port}`)
    })

{: data-line=“2,3”}

Add `{: data-line="2,3"}` to add multiple line highlights.

### Setup blocks

    import React from 'react'

{: .-setup}

    class Hello extends React.Component {
      render () {
        return <span>Hello</span>
      }
    }

Add `{: .-setup}` to a `pre` or `table` or `ul`.

### Long lines

    function createNode(nodeName: string, options: { key: string }) {
      return true
    }

Long lines will have scrollbars.

### Line wrapping

    <script>(function(d,s){if(window.Promise&&[].includes&&Object.assign&&window.Map)return;var js,sc=d.getElementsByTagName(s)[0];js=d.createElement(s);js.src='https://cdn.polyfill.io/v2/polyfill.min.js';sc.parentNode.insertBefore(js, sc);}(document,'script'))</script>

{: .-wrap}

Add `-wrap` to wrap long lines.

Lists
-----

{: .-three-column}

### Lists

-   This is
-   a list
-   with a few items

Here’s an extra paragraph after the list.

### Lists with headings

#### Part 1

-   `createElement()`
-   `componentDidMount()`
-   `componentWillUnmount()`

#### Part 2

-   `shouldComponentUpdate()`
-   `componentWillReceiveProps()`

Here’s an extra paragraph after the list.

List columns
------------

{: .-one-column}

### Six columns

-   One
-   Two
-   Three
-   Four
-   Five
-   Six
-   Seven
-   Eight
-   Nine
-   Ten
-   Eleven {: .-six-column}

Add `{: .-six-column}` to make large lists.

### Four columns

-   One
-   Two
-   Three
-   Four
-   Five
-   Six
-   Seven
-   Eight
-   Nine
-   Ten
-   Eleven {: .-four-column}

Add `{: .-four-column}` to make large lists.

### Also see

-   One
-   Two
-   Three
-   Four
-   Five
-   Six
-   Seven
-   Eight
-   Nine
-   Ten {: .-also-see}

Add `{: .-also-see}`.

Paragraphs
----------

{: .-three-column}

### Basic paragraphs

This is a basic section with paragraphs in it. When paragraphs are the first elements in an H3 section’s body, they appear as white.

### Basic paragraphs

    ···

When paragraphs appear after `pre`/`table`/`ul`, they appear with a gray background.

### Preludes

Here’s a prelude paragraph. Add `{: .-setup}` to make paragraphs appear with a gray background. {: .-setup}

    ···

### Crosslink

Add `{: .-crosslink}` to make big loud external links:

    ···

[Home](/) {: .-crosslink}

Tables
------

{: .-three-column}

### Basic table

#### Date

<table><thead><tr class="header"><th>Example</th><th>Output</th></tr></thead><tbody><tr class="odd"><td><code>%m/%d/%Y</code></td><td><code>06/05/2013</code></td></tr><tr class="even"><td><code>%A, %B %e, %Y</code></td><td><code>Sunday, June 5, 2013</code></td></tr><tr class="odd"><td><code>%b %e %a</code></td><td><code>Jun 5 Sun</code></td></tr></tbody></table>

#### Time

<table><thead><tr class="header"><th>Example</th><th>Output</th></tr></thead><tbody><tr class="odd"><td><code>%H:%M</code></td><td><code>23:05</code></td></tr><tr class="even"><td><code>%I:%M %p</code></td><td><code>11:05 PM</code></td></tr></tbody></table>

This is a basic table with h4’s.

### Shortcuts

`V` | Vector |  
`P` | Pencil |  
`T` | Text |  
`L` | Line |  
`R` | Rectangle |  
`O` | Oval |  
`U` | Rounded |

{: .-shortcuts}

Add `{: .-shortcuts}` to tables.

### With headers

<table><thead><tr class="header"><th>Prefix</th><th>Example</th><th>What</th></tr></thead><tbody><tr class="odd"><td><code>//</code></td><td><code>//hr[@class='edge']</code></td><td>Anywhere</td></tr><tr class="even"><td><code>./</code></td><td><code>./a</code></td><td>Relative</td></tr><tr class="odd"><td><code>/</code></td><td><code>/html/body/div</code></td><td>Root</td></tr></tbody></table>

{: .-headers}

Add `{: .-headers}` to add headers.

Two columns
-----------

### One

    ···

### Two

    ···

Left reference
--------------

{: .-left-reference}

### One

    ···
    ···
    ···
    ···
    ···
    ···
    ···
    ···

### Two

    ···

### Three

    ···

One column
----------

{: .-one-column}

### One

    ···
