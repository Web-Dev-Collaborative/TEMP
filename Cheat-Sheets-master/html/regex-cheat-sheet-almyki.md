;

A Gentle Introduction to Regex
==============================

------------------------------------------------------------------------

INDEX
-----

-   [Just a string](#just-a-string)
-   [The Star Operator `*`](#the-star-operator)
-   [The Optional Operator `?`](#the-optional-operator)
-   [The Plus Operator `+`](#the-plus-operator)
-   [The Dot Operator `.`](#the-dot-operator)
-   [The Hat Operator (outside \[ \]) `^`](#the-hat-operator-outside)
-   [The Dollar Sign Operator `$`](#the-dollar-sign-operator)
-   [The Square Brackets `[ ]`](#the-square-brackets)
-   [The Dash Operator (only inside \[ \]) `[ - ]`](#the-dash-operator-only-inside-)
-   [The Hat Operator (only inside \[ \]) `[ ^ ]`](#the-hat-operator-only-inside)
-   [The Parentheses `( )`](#the-parentheses)
-   [Escape Operator Characters `\🔣`](#escape-operator-characters)
-   [Special Character Classes `\🔠`](#special-character-classes)

------------------------------------------------------------------------

### `regex example here`

*regex example breakdown here*

<table><thead><tr class="header"><th style="text-align: left;">Inputs</th><th style="text-align: center;">Match</th></tr></thead><tbody><tr class="odd"><td style="text-align: left;"><code>what</code> is the pattern?</td><td style="text-align: center;">y/n</td></tr><tr class="even"><td style="text-align: left;">what is<code></code>the matter?</td><td style="text-align: center;">y/n</td></tr><tr class="odd"><td style="text-align: left;">is your name Pa<code>t?</code></td><td style="text-align: center;">y/n</td></tr></tbody></table>

------------------------------------------------------------------------

Just a string
-------------

### matches *exactly*

### `pat`

*exactly "pat"*

<table><thead><tr class="header"><th style="text-align: left;">Inputs</th><th style="text-align: center;">Match</th></tr></thead><tbody><tr class="odd"><td style="text-align: left;">what is the <code>pat</code>tern?</td><td style="text-align: center;">y</td></tr><tr class="even"><td style="text-align: left;">what is the matter?</td><td style="text-align: center;">n</td></tr><tr class="odd"><td style="text-align: left;">is your name Pat?</td><td style="text-align: center;">n</td></tr></tbody></table>

### `the`

*exactly "the"*

<table><thead><tr class="header"><th style="text-align: left;">Inputs</th><th style="text-align: center;">Match</th></tr></thead><tbody><tr class="odd"><td style="text-align: left;">what is <code>the</code> pattern?</td><td style="text-align: center;">y</td></tr><tr class="even"><td style="text-align: left;">what is <code>the</code> matter?</td><td style="text-align: center;">y</td></tr><tr class="odd"><td style="text-align: left;">is your name Pat?</td><td style="text-align: center;">n</td></tr></tbody></table>

The Star Operator `*`
---------------------

### Zero or more of what's right before it

### `th*e`

*t, then zero or more h, then e*

<table><thead><tr class="header"><th style="text-align: left;">Inputs</th><th style="text-align: center;">Match</th></tr></thead><tbody><tr class="odd"><td style="text-align: left;">what is <code>the</code> pat<code>te</code>rn?</td><td style="text-align: center;">y</td></tr><tr class="even"><td style="text-align: left;">what is <code>the</code> mat<code>te</code>r?</td><td style="text-align: center;">y</td></tr><tr class="odd"><td style="text-align: left;">is your name Pat?</td><td style="text-align: center;">n</td></tr></tbody></table>

### `at*`

*a, then zero or more t*

<table><thead><tr class="header"><th style="text-align: left;">Inputs</th><th style="text-align: center;">Match</th></tr></thead><tbody><tr class="odd"><td style="text-align: left;">wh<code>at</code> is the p<code>att</code>ern?</td><td style="text-align: center;">y</td></tr><tr class="even"><td style="text-align: left;">wh<code>at</code> is the m<code>att</code>er?</td><td style="text-align: center;">y</td></tr><tr class="odd"><td style="text-align: left;">is your n<code>a</code>me P<code>at</code>?</td><td style="text-align: center;">y</td></tr></tbody></table>

The Optional Operator `?`
-------------------------

### Zero or more of what's right before it

### `at?t`

*a, zero or one 1, t*

<table><thead><tr class="header"><th style="text-align: left;">Inputs</th><th style="text-align: center;">Match</th></tr></thead><tbody><tr class="odd"><td style="text-align: left;">wh<code>at</code> is the p<code>att</code>ern?</td><td style="text-align: center;">y</td></tr><tr class="even"><td style="text-align: left;">wh<code>at</code> is the m<code>att</code>er?</td><td style="text-align: center;">y</td></tr><tr class="odd"><td style="text-align: left;">is your name P<code>at</code>?</td><td style="text-align: center;">n</td></tr></tbody></table>

### `att?`

*a, t, zero or one t*

<table><thead><tr class="header"><th style="text-align: left;">Inputs</th><th style="text-align: center;">Match</th></tr></thead><tbody><tr class="odd"><td style="text-align: left;">wh<code>at</code> is the p<code>att</code>ern?</td><td style="text-align: center;">y</td></tr><tr class="even"><td style="text-align: left;">wh<code>at</code> is the m<code>att</code>er?</td><td style="text-align: center;">y</td></tr><tr class="odd"><td style="text-align: left;">is your name P<code>at</code>?</td><td style="text-align: center;">y</td></tr></tbody></table>

### `h?at`

*zero or one h, a, t*

<table><thead><tr class="header"><th style="text-align: left;">Inputs</th><th style="text-align: center;">Match</th></tr></thead><tbody><tr class="odd"><td style="text-align: left;">w<code>hat</code> is the p<code>at</code>tern?</td><td style="text-align: center;">y</td></tr><tr class="even"><td style="text-align: left;">w<code>hat</code> is the m<code>at</code>ter?</td><td style="text-align: center;">y</td></tr><tr class="odd"><td style="text-align: left;">is your name P<code>at</code>?</td><td style="text-align: center;">y</td></tr></tbody></table>

The Plus Operator `+`
---------------------

### One or more of what's right before it

### `at+`

*a, one or more t*

<table><thead><tr class="header"><th style="text-align: left;">Inputs</th><th style="text-align: center;">Match</th></tr></thead><tbody><tr class="odd"><td style="text-align: left;">wh<code>at</code> is the p<code>att</code>ern?</td><td style="text-align: center;">y</td></tr><tr class="even"><td style="text-align: left;">wh<code>at</code> is the m<code>att</code>er?</td><td style="text-align: center;">y</td></tr><tr class="odd"><td style="text-align: left;">is your name P<code>at</code>?</td><td style="text-align: center;">y</td></tr></tbody></table>

### `r +`

*r, one or more spaces*

<table><thead><tr class="header"><th style="text-align: left;">Inputs</th><th style="text-align: center;">Match</th></tr></thead><tbody><tr class="odd"><td style="text-align: left;">what is the pattern?</td><td style="text-align: center;">n</td></tr><tr class="even"><td style="text-align: left;">what is the matter?</td><td style="text-align: center;">n</td></tr><tr class="odd"><td style="text-align: left;">what is you<code>r</code>name Pat?</td><td style="text-align: center;">y</td></tr></tbody></table>

The Dot Operator `.`
--------------------

### Any one character

### `e .`

*e, space, any character*

<table><thead><tr class="header"><th style="text-align: left;">Inputs</th><th style="text-align: center;">Match</th></tr></thead><tbody><tr class="odd"><td style="text-align: left;">what is th<code>e p</code>attern?</td><td style="text-align: center;">y</td></tr><tr class="even"><td style="text-align: left;">what is th<code>e m</code>atter?</td><td style="text-align: center;">y</td></tr><tr class="odd"><td style="text-align: left;">is your nam<code>e P</code>at?</td><td style="text-align: center;">y</td></tr></tbody></table>

### `r..`

*r, any character, any character*

<table><thead><tr class="header"><th style="text-align: left;">Inputs</th><th style="text-align: center;">Match</th></tr></thead><tbody><tr class="odd"><td style="text-align: left;">what is the patte<code>rn?</code></td><td style="text-align: center;">y</td></tr><tr class="even"><td style="text-align: left;">what is the matter?</td><td style="text-align: center;">n</td></tr><tr class="odd"><td style="text-align: left;">is you<code>r n</code>ame Pat?</td><td style="text-align: center;">y</td></tr></tbody></table>

The Hat Operator (outside `[ ]`) `^`
------------------------------------

### Start of input anchor

### `^is`

*start of input, i, s*

<table><thead><tr class="header"><th style="text-align: left;">Inputs</th><th style="text-align: center;">Match</th></tr></thead><tbody><tr class="odd"><td style="text-align: left;">what is the the pattern?</td><td style="text-align: center;">n</td></tr><tr class="even"><td style="text-align: left;">what is the matter?</td><td style="text-align: center;">n</td></tr><tr class="odd"><td style="text-align: left;"><code>is</code> your name Pat?</td><td style="text-align: center;">y</td></tr></tbody></table>

The Dollar Sign Operator `$`
----------------------------

### End of input anchor

### `at.$`

*a, t, any character, end of input*

<table><thead><tr class="header"><th style="text-align: left;">Inputs</th><th style="text-align: center;">Match</th></tr></thead><tbody><tr class="odd"><td style="text-align: left;">what is the pattern?</td><td style="text-align: center;">n</td></tr><tr class="even"><td style="text-align: left;">what is the matter?</td><td style="text-align: center;">n</td></tr><tr class="odd"><td style="text-align: left;">is your name P<code>at?</code></td><td style="text-align: center;">y</td></tr></tbody></table>

The Square Brackets `[ ]`
-------------------------

### Your choice of character

### `a[tm]e`

*a, t or m, e*

<table><thead><tr class="header"><th style="text-align: left;">Inputs</th><th style="text-align: center;">Match</th></tr></thead><tbody><tr class="odd"><td style="text-align: left;">what is the pattern?</td><td style="text-align: center;">n</td></tr><tr class="even"><td style="text-align: left;">what is the matter?</td><td style="text-align: center;">n</td></tr><tr class="odd"><td style="text-align: left;">is your n<code>ame</code> Pat?</td><td style="text-align: center;">y</td></tr></tbody></table>

### `a[tm]+e`

*a, one or more (t or m), e*

<table><thead><tr class="header"><th style="text-align: left;">Inputs</th><th style="text-align: center;">Match</th></tr></thead><tbody><tr class="odd"><td style="text-align: left;">what is the p<code>atte</code>rn?</td><td style="text-align: center;">y</td></tr><tr class="even"><td style="text-align: left;">what is the m<code>atte</code>r?</td><td style="text-align: center;">y</td></tr><tr class="odd"><td style="text-align: left;">is your n<code>ame</code> Pat?</td><td style="text-align: center;">y</td></tr></tbody></table>

### `[whP]+at`

*one or more (w, h, P), a, t*

<table><thead><tr class="header"><th style="text-align: left;">Inputs</th><th style="text-align: center;">Match</th></tr></thead><tbody><tr class="odd"><td style="text-align: left;"><code>what</code> is the pattern?</td><td style="text-align: center;">y</td></tr><tr class="even"><td style="text-align: left;"><code>what</code> is the matter?</td><td style="text-align: center;">y</td></tr><tr class="odd"><td style="text-align: left;">is your name <code>Pat</code>?</td><td style="text-align: center;">y</td></tr></tbody></table>

The Dash Operator (only inside `[ ]`) `[ - ]`
---------------------------------------------

### A range of characters

### `[a-zA-Z-at]`

*any lower/upper letter, a, t*

<table><thead><tr class="header"><th style="text-align: left;">Inputs</th><th style="text-align: center;">Match</th></tr></thead><tbody><tr class="odd"><td style="text-align: left;">w<code>hat</code> is the <code>pat</code>tern?</td><td style="text-align: center;">y</td></tr><tr class="even"><td style="text-align: left;">w<code>hat</code> is the <code>mat</code>ter?</td><td style="text-align: center;">y</td></tr><tr class="odd"><td style="text-align: left;">is your name <code>Pat</code>?</td><td style="text-align: center;">y</td></tr></tbody></table>

### `[a-z] [v-z]`

*any lower letter, space, vwxyz*

<table><thead><tr class="header"><th style="text-align: left;">Inputs</th><th style="text-align: center;">Match</th></tr></thead><tbody><tr class="odd"><td style="text-align: left;">what is the pattern?</td><td style="text-align: center;">n</td></tr><tr class="even"><td style="text-align: left;">what is the matter?</td><td style="text-align: center;">n</td></tr><tr class="odd"><td style="text-align: left;">i<code>s y</code>our name Pat?</td><td style="text-align: center;">y</td></tr></tbody></table>

### `[0-9]`

*any number character*

<table><thead><tr class="header"><th style="text-align: left;">Inputs</th><th style="text-align: center;">Match</th></tr></thead><tbody><tr class="odd"><td style="text-align: left;">what is the pattern?</td><td style="text-align: center;">n</td></tr><tr class="even"><td style="text-align: left;">what is the matter?</td><td style="text-align: center;">n</td></tr><tr class="odd"><td style="text-align: left;">is your name Pat?</td><td style="text-align: center;">n</td></tr></tbody></table>

The Hat Operator (only inside `[ ]`) `[ ^ ]`
--------------------------------------------

### Those characters? None of them (like a NOT operator)

### `[^a-zA-Z]`

*any non-letter character*

<table><thead><tr class="header"><th style="text-align: left;">Inputs</th><th style="text-align: center;">Match</th></tr></thead><tbody><tr class="odd"><td style="text-align: left;">what<code></code>is<code></code>the<code></code>pattern<code>?</code></td><td style="text-align: center;">y</td></tr><tr class="even"><td style="text-align: left;">what<code></code>is<code></code>the<code></code>matter<code>?</code></td><td style="text-align: center;">y</td></tr><tr class="odd"><td style="text-align: left;">is<code></code>your<code></code>name<code></code>Pat<code>?</code></td><td style="text-align: center;">y</td></tr></tbody></table>

The Parentheses `( )`
---------------------

### Used for grouping

> **NOTE** Parentheses are primarily used to capture groups of characters for  
> replacements, which is covered more later~

### `^(is)`

*start of input, i, s*

> NOTE Doesn't really effect things...

<table><thead><tr class="header"><th style="text-align: left;">Inputs</th><th style="text-align: center;">Match</th></tr></thead><tbody><tr class="odd"><td style="text-align: left;">what is the pattern?</td><td style="text-align: center;">n</td></tr><tr class="even"><td style="text-align: left;">what is the matter?</td><td style="text-align: center;">n</td></tr><tr class="odd"><td style="text-align: left;"><code>is</code> your name Pat?</td><td style="text-align: center;">y</td></tr></tbody></table>

### `at( is)?`

*a, t, optional(space, i, s)*

> NOTE Compare with previous example!

<table><thead><tr class="header"><th style="text-align: left;">Inputs</th><th style="text-align: center;">Match</th></tr></thead><tbody><tr class="odd"><td style="text-align: left;">wh<code>at is</code> the pattern?</td><td style="text-align: center;">y</td></tr><tr class="even"><td style="text-align: left;">wh<code>at is</code> the matter?</td><td style="text-align: center;">y</td></tr><tr class="odd"><td style="text-align: left;">is your name P<code>at</code>?</td><td style="text-align: center;">y</td></tr></tbody></table>

Escape Operator Characters `\🔣`
-------------------------------

### `at?\?`

*a, optional t, question mark*

> NOTE The backslash can escape the above operators like so: `\*` `\?` `\^`  
> This example is shown to demonstrate this feature.

<table><thead><tr class="header"><th style="text-align: left;">Inputs</th><th style="text-align: center;">Match</th></tr></thead><tbody><tr class="odd"><td style="text-align: left;">what is the pattern?</td><td style="text-align: center;">n</td></tr><tr class="even"><td style="text-align: left;">what is the matter?</td><td style="text-align: center;">n</td></tr><tr class="odd"><td style="text-align: left;">is your name P<code>at?</code></td><td style="text-align: center;">y</td></tr></tbody></table>

Special Character Classes `\🔠`
------------------------------

*Convenient shorthands*

<table><thead><tr class="header"><th style="text-align: center;">Syntax</th><th>Meaning</th></tr></thead><tbody><tr class="odd"><td style="text-align: center;"><code>\s</code></td><td>whitespace (space, tab, newline)</td></tr><tr class="even"><td style="text-align: center;"><code>\d</code></td><td>digit</td></tr><tr class="odd"><td style="text-align: center;"><code>\w</code></td><td>word character (letter, digit, _)</td></tr><tr class="even"><td style="text-align: center;"><code>\S</code></td><td>not whitespace</td></tr><tr class="odd"><td style="text-align: center;"><code>\W</code></td><td>not a word character</td></tr></tbody></table>

-   [A Gentle Introduction to Regex](#a-gentle-introduction-to-regex)
    -   [INDEX](#index)
        -   [`regex example here`](#regex-example-here)
    -   [Just a string](#just-a-string)
        -   [matches *exactly*](#matches-exactly)
        -   [`pat`](#pat)
        -   [`the`](#the)
    -   [The Star Operator `*`](#the-star-operator)
        -   [Zero or more of what's right before it](#zero-or-more-of-whats-right-before-it)
        -   [`th*e`](#the-1)
        -   [`at*`](#at)
    -   [The Optional Operator `?`](#the-optional-operator)
        -   [Zero or more of what's right before it](#zero-or-more-of-whats-right-before-it-1)
        -   [`at?t`](#att)
        -   [`att?`](#att-1)
        -   [`h?at`](#hat)
    -   [The Plus Operator `+`](#the-plus-operator)
        -   [One or more of what's right before it](#one-or-more-of-whats-right-before-it)
        -   [`at+`](#at-1)
        -   [`r +`](#r)
    -   [The Dot Operator `.`](#the-dot-operator)
        -   [Any one character](#any-one-character)
        -   [`e .`](#e)
        -   [`r..`](#r-1)
    -   [The Hat Operator (outside `[ ]`) `^`](#the-hat-operator-outside)
        -   [Start of input anchor](#start-of-input-anchor)
        -   [`^is`](#is)
    -   [The Dollar Sign Operator `$`](#the-dollar-sign-operator)
        -   [End of input anchor](#end-of-input-anchor)
        -   [`at.$`](#at-2)
    -   [The Square Brackets `[ ]`](#the-square-brackets)
        -   [Your choice of character](#your-choice-of-character)
        -   [`a[tm]e`](#atme)
        -   [`a[tm]+e`](#atme-1)
        -   [`[whP]+at`](#whpat)
    -   [The Dash Operator (only inside `[ ]`) `[ - ]`](#the-dash-operator-only-inside-)
        -   [A range of characters](#a-range-of-characters)
        -   [`[a-zA-Z-at]`](#a-za-z-at)
        -   [`[a-z] [v-z]`](#a-z-v-z)
        -   [`[0-9]`](#0-9)
    -   [The Hat Operator (only inside `[ ]`) `[ ^ ]`](#the-hat-operator-only-inside)
        -   [Those characters? None of them (like a NOT operator)](#those-characters-none-of-them-like-a-not-operator)
        -   [\`\`](#a-za-z)
    -   [The Parentheses `( )`](#the-parentheses)
        -   [Used for grouping](#used-for-grouping)
        -   [`^(is)`](#is-1)
        -   [`at( is)?`](#at-is)
    -   [Escape Operator Characters `\🔣`](#escape-operator-characters)
        -   [`at?\?`](#at-3)
    -   [Special Character Classes `\🔠`](#special-character-classes)

<span id="sidebar-toc-btn">≡</span>
