;

Getting started
---------------

{: .-three-column}

### Exiting

{: .-prime}

<table><thead><tr class="header"><th>Shortcut</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>:qa</code></td><td>Close all files</td></tr><tr class="even"><td><code>:qa!</code></td><td>Close all files, abandon changes</td></tr><tr class="odd"><td>—</td><td>—</td></tr><tr class="even"><td><code>:w</code></td><td>Save</td></tr><tr class="odd"><td><code>:wq</code> <em>/</em> <code>:x</code></td><td>Save and close file</td></tr><tr class="even"><td>—</td><td>—</td></tr><tr class="odd"><td><code>:q</code></td><td>Close file</td></tr><tr class="even"><td><code>:q!</code></td><td>Close file, abandon changes</td></tr><tr class="odd"><td>—</td><td>—</td></tr><tr class="even"><td><code>ZZ</code></td><td>Save and quit</td></tr><tr class="odd"><td><code>ZQ</code></td><td>Quit without checking changes</td></tr></tbody></table>

{: .-shortcuts}

### Navigating

<table><thead><tr class="header"><th>Shortcut</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>h</code> <code>j</code> <code>k</code> <code>l</code></td><td>Arrow keys</td></tr><tr class="even"><td><code>&lt;C-U&gt;</code> <em>/</em> <code>&lt;C-D&gt;</code></td><td>Page up/page down</td></tr></tbody></table>

{: .-shortcuts}

#### Words

Shortcut | Description |

ff| — | — | | `b` */* `w` | Previous/next word | | `ge` */* `e` | Previous/next end of word | {: .-shortcuts}

#### Line

<table><thead><tr class="header"><th>Shortcut</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>0</code> <em>(zero)</em></td><td>Start of line</td></tr><tr class="even"><td><code>^</code></td><td>Start of line <em>(after whitespace)</em></td></tr><tr class="odd"><td><code>$</code></td><td>End of line</td></tr></tbody></table>

{: .-shortcuts}

#### Character

`fc` | Go forward to character `c` |  
`Fc` | Go backward to character `c` |

{: .-shortcuts}

#### Document

<table><thead><tr class="header"><th>Shortcut</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>gg</code></td><td>First line</td></tr><tr class="even"><td><code>G</code></td><td>Last line</td></tr><tr class="odd"><td><code>:n</code></td><td>Go to line <code>n</code></td></tr><tr class="even"><td><code>nG</code></td><td>Go to line <code>n</code></td></tr></tbody></table>

{: .-shortcuts}

#### Window

<table><thead><tr class="header"><th>Shortcut</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>zz</code></td><td>Center this line</td></tr><tr class="even"><td><code>zt</code></td><td>Top this line</td></tr><tr class="odd"><td><code>H</code></td><td>Move to top of screen</td></tr><tr class="even"><td><code>M</code></td><td>Move to middle of screen</td></tr><tr class="odd"><td><code>L</code></td><td>Move to bottom of screen</td></tr></tbody></table>

{: .-shortcuts}

#### Tab pages

<table><thead><tr class="header"><th>Shortcut</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>:tabedit [file]</code></td><td>Edit file in a new tab</td></tr><tr class="even"><td><code>:tabfind [file]</code></td><td>Open file if exists in new tab</td></tr><tr class="odd"><td><code>:tabclose</code></td><td>Close current tab</td></tr><tr class="even"><td><code>:tabs</code></td><td>List all tabs</td></tr><tr class="odd"><td><code>:tabfirst</code></td><td>Go to first tab</td></tr><tr class="even"><td><code>:tablast</code></td><td>Go to last tab</td></tr><tr class="odd"><td><code>:tabn</code></td><td>Go to next tab</td></tr><tr class="even"><td><code>:tabp</code></td><td>Go to previous tab</td></tr></tbody></table>

### Editing

<table><thead><tr class="header"><th>Shortcut</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>a</code></td><td>Append</td></tr><tr class="even"><td><code>i</code></td><td>Insert</td></tr><tr class="odd"><td><code>o</code></td><td>Next line</td></tr><tr class="even"><td><code>O</code></td><td>Previous line</td></tr><tr class="odd"><td>—</td><td>—</td></tr><tr class="even"><td><code>s</code></td><td>Delete char and insert</td></tr><tr class="odd"><td><code>S</code></td><td>Delete line and insert</td></tr><tr class="even"><td><code>C</code></td><td>Delete until end of line and insert</td></tr><tr class="odd"><td>—</td><td>—</td></tr><tr class="even"><td><code>r</code></td><td>Replace one character</td></tr><tr class="odd"><td><code>R</code></td><td>Enter Replace mode</td></tr><tr class="even"><td>—</td><td>—</td></tr><tr class="odd"><td><code>u</code></td><td>Undo changes</td></tr><tr class="even"><td><code>&lt;C-R&gt;</code></td><td>Redo changes</td></tr></tbody></table>

{: .-shortcuts}

### Exiting insert mode

<table><thead><tr class="header"><th>Shortcut</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>Esc</code> <em>/</em> <code>&lt;C-[&gt;</code></td><td>Exit insert mode</td></tr><tr class="even"><td><code>&lt;C-C&gt;</code></td><td>Exit insert mode, and abort current command</td></tr></tbody></table>

{: .-shortcuts}

### Clipboard

<table><thead><tr class="header"><th>Shortcut</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>x</code></td><td>Delete character</td></tr><tr class="even"><td>—</td><td>—</td></tr><tr class="odd"><td><code>dd</code></td><td>Delete line <em>(Cut)</em></td></tr><tr class="even"><td><code>yy</code></td><td>Yank line <em>(Copy)</em></td></tr><tr class="odd"><td>—</td><td>—</td></tr><tr class="even"><td><code>p</code></td><td>Paste</td></tr><tr class="odd"><td><code>P</code></td><td>Paste before</td></tr></tbody></table>

{: .-shortcuts}

### Visual mode

<table><thead><tr class="header"><th>Shortcut</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>v</code></td><td>Enter visual mode</td></tr><tr class="even"><td><code>V</code></td><td>Enter visual line mode</td></tr><tr class="odd"><td><code>&lt;C-V&gt;</code></td><td>Enter visual block mode</td></tr></tbody></table>

{: .-shortcuts}

#### In visual mode

<table><thead><tr class="header"><th>Shortcut</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>d</code> <em>/</em> <code>x</code></td><td>Delete selection</td></tr><tr class="even"><td><code>s</code></td><td>Replace selection</td></tr><tr class="odd"><td><code>y</code></td><td>Yank selection <em>(Copy)</em></td></tr></tbody></table>

{: .-shortcuts}

See [Operators](#operators) for other things you can do.

Operators
---------

{: .-three-column}

### Usage

{: .-prime}

Operators let you operate in a range of text (defined by *motion*). These are performed in normal mode. {: .-setup}

`d` | `w` |  
Operator | Motion |

{: .-css-breakdown}

### Operators list

<table><thead><tr class="header"><th>Shortcut</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>d</code></td><td>Delete</td></tr><tr class="even"><td><code>y</code></td><td>Yank <em>(copy)</em></td></tr><tr class="odd"><td><code>c</code></td><td>Change <em>(delete then insert)</em></td></tr><tr class="even"><td>—</td><td>—</td></tr><tr class="odd"><td><code>&gt;</code></td><td>Indent right</td></tr><tr class="even"><td><code>&lt;</code></td><td>Indent left</td></tr><tr class="odd"><td>—</td><td>—</td></tr><tr class="even"><td><code>g~</code></td><td>Swap case</td></tr><tr class="odd"><td><code>gU</code></td><td>Uppercase</td></tr><tr class="even"><td><code>gu</code></td><td>Lowercase</td></tr><tr class="odd"><td>—</td><td>—</td></tr><tr class="even"><td><code>!</code></td><td>Filter through external program</td></tr></tbody></table>

{: .-shortcuts}

See `:help operator`

### Examples

Combine operators with *motions* to use them. {: .-setup}

<table><thead><tr class="header"><th>Shortcut</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>d</code><em>d</em></td><td><em>(repeat the letter)</em> Delete current line</td></tr><tr class="even"><td><code>d</code><em>w</em></td><td>Delete to next word</td></tr><tr class="odd"><td><code>d</code><em>b</em></td><td>Delete to beginning of word</td></tr><tr class="even"><td><em>2</em><code>dd</code></td><td>Delete 2 lines</td></tr><tr class="odd"><td><code>d</code><em>ip</em></td><td>Delete a text object <em>(inside paragraph)</em></td></tr><tr class="even"><td><em>(in visual mode)</em> <code>d</code></td><td>Delete selection</td></tr></tbody></table>

See: `:help motion.txt`

Text objects
------------

{: .-three-column}

### Usage

{: .-prime}

Text objects let you operate (with an *operator*) in or around text blocks (*objects*). {: .-setup}

`v` | `i` | `p` |  
Operator | \[i\]nside or \[a\]round | Text object |

{: .-css-breakdown}

### Text objects

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th>Shortcut</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>p</code></td><td>Paragraph</td></tr><tr class="even"><td><code>w</code></td><td>Word</td></tr><tr class="odd"><td><code>s</code></td><td>Sentence</td></tr><tr class="even"><td>—</td><td>—</td></tr><tr class="odd"><td><code>[</code> <code>(</code> <code>{</code> <code>&lt;</code></td><td>A [], (), or {} block</td></tr><tr class="even"><td><code>'</code> <code>"</code> <code>&lt;/code&gt; | A quoted string       | | ---                    | ---                   | |</code>b<code>| A block [(            | |</code>B<code>| A block in [{         | |</code>t`</td><td>A XML tag block</td></tr></tbody></table>

{: .-shortcuts}

### Examples

<table><thead><tr class="header"><th>Shortcut</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>vip</code></td><td>Select paragraph</td></tr><tr class="even"><td><code>vipipipip</code></td><td>Select more</td></tr><tr class="odd"><td>—</td><td>—</td></tr><tr class="even"><td><code>yip</code></td><td>Yank inner paragraph</td></tr><tr class="odd"><td><code>yap</code></td><td>Yank paragraph (including newline)</td></tr><tr class="even"><td>—</td><td>—</td></tr><tr class="odd"><td><code>dip</code></td><td>Delete inner paragraph</td></tr><tr class="even"><td><code>cip</code></td><td>Change inner paragraph</td></tr></tbody></table>

{: .-shortcuts}

See [Operators](#operators) for other things you can do.

### Diff

<table><thead><tr class="header"><th>Shortcut</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>gvimdiff file1 file2 [file3]</code></td><td>See differencies between files, in HMI</td></tr></tbody></table>

Misc
----

### Folds

<table><thead><tr class="header"><th>Shortcut</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>zo</code> <em>/</em> <code>zO</code></td><td>Open</td></tr><tr class="even"><td><code>zc</code> <em>/</em> <code>zC</code></td><td>Close</td></tr><tr class="odd"><td><code>za</code> <em>/</em> <code>zA</code></td><td>Toggle</td></tr><tr class="even"><td>—</td><td>—</td></tr><tr class="odd"><td><code>zv</code></td><td>Open folds for this line</td></tr><tr class="even"><td>—</td><td>—</td></tr><tr class="odd"><td><code>zM</code></td><td>Close all</td></tr><tr class="even"><td><code>zR</code></td><td>Open all</td></tr><tr class="odd"><td>—</td><td>—</td></tr><tr class="even"><td><code>zm</code></td><td>Fold more <em>(foldlevel += 1)</em></td></tr><tr class="odd"><td><code>zr</code></td><td>Fold less <em>(foldlevel -= 1)</em></td></tr><tr class="even"><td>—</td><td>—</td></tr><tr class="odd"><td><code>zx</code></td><td>Update folds</td></tr></tbody></table>

{: .-shortcuts}

Uppercase ones are recursive (eg, `zO` is open recursively).

### Navigation

<table><thead><tr class="header"><th>Shortcut</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>[(</code> <code>[{</code> <code>[&lt;</code></td><td>Previous <code>(</code> or <code>{</code> or <code>&lt;</code></td></tr><tr class="even"><td><code>])</code></td><td>Next</td></tr><tr class="odd"><td>—</td><td>—</td></tr><tr class="even"><td><code>[m</code></td><td>Previous method start</td></tr><tr class="odd"><td><code>[M</code></td><td>Previous method end</td></tr></tbody></table>

{: .-shortcuts}

### Jumping

<table><thead><tr class="header"><th>Shortcut</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>&lt;C-O&gt;</code></td><td>Go back to previous location</td></tr><tr class="even"><td><code>&lt;C-I&gt;</code></td><td>Go forward</td></tr><tr class="odd"><td>—</td><td>—</td></tr><tr class="even"><td><code>gf</code></td><td>Go to file in cursor</td></tr></tbody></table>

{: .-shortcuts}

### Counters

<table><thead><tr class="header"><th>Shortcut</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>&lt;C-A&gt;</code></td><td>Increment number</td></tr><tr class="even"><td><code>&lt;C-X&gt;</code></td><td>Decrement</td></tr></tbody></table>

{: .-shortcuts}

### Windows

`z{height}<Cr>` | Resize pane to `{height}` lines tall |

### Tags

<table><thead><tr class="header"><th>Shortcut</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>:tag Classname</code></td><td>Jump to first definition of Classname</td></tr><tr class="even"><td>—</td><td>—</td></tr><tr class="odd"><td><code>&lt;C-]&gt;</code></td><td>Jump to definition</td></tr><tr class="even"><td><code>g]</code></td><td>See all definitions</td></tr><tr class="odd"><td><code>&lt;C-T&gt;</code></td><td>Go back to last tag</td></tr><tr class="even"><td><code>&lt;C-O&gt; &lt;C-I&gt;</code></td><td>Back/forward</td></tr><tr class="odd"><td>—</td><td>—</td></tr><tr class="even"><td><code>:tselect Classname</code></td><td>Find definitions of Classname</td></tr><tr class="odd"><td><code>:tjump Classname</code></td><td>Find definitions of Classname (auto-select 1st)</td></tr></tbody></table>

{: .-shortcuts}

### Case

<table><thead><tr class="header"><th>Shortcut</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>~</code></td><td>Toggle case (Case =&gt; cASE)</td></tr><tr class="even"><td><code>gU</code></td><td>Uppercase</td></tr><tr class="odd"><td><code>gu</code></td><td>Lowercase</td></tr><tr class="even"><td>—</td><td>—</td></tr><tr class="odd"><td><code>gUU</code></td><td>Uppercase current line (also <code>gUgU</code>)</td></tr><tr class="even"><td><code>guu</code></td><td>Lowercase current line (also <code>gugu</code>)</td></tr></tbody></table>

{: .-shortcuts}

Do these in visual or normal mode.

### Marks

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th>Shortcut</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>^&lt;/code&gt; | Last position of cursor in insert mode             | | &lt;code&gt;</code>.</td><td>Last change</td></tr><tr class="even"><td><code>`&lt;/code&gt; | Last jump                                          | | ---             | ---                                                | |</code>ma<code>| Mark this cursor position as</code>a<code>| | &lt;code&gt;</code>a</td><td>Jump to the cursor position <code>a</code></td></tr><tr class="odd"><td><code>'a</code></td><td>Jump to the beginning of the line with position <code>a</code></td></tr></tbody></table>

{: .-shortcuts}

### Misc

<table><thead><tr class="header"><th>Shortcut</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>.</code></td><td>Repeat last command</td></tr><tr class="even"><td><code>]p</code></td><td>Paste under the current indentation level</td></tr><tr class="odd"><td>—</td><td>—</td></tr><tr class="even"><td><code>:ff=unix</code></td><td>Convert Windows line endings to Unix line endings</td></tr></tbody></table>

{: .-shortcuts}

### Command line

<table><thead><tr class="header"><th>Shortcut</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>&lt;C-R&gt;&lt;C-W&gt;</code></td><td>Insert current word into the command line</td></tr><tr class="even"><td><code>&lt;C-R&gt;"</code></td><td>Paste from " register</td></tr><tr class="odd"><td><code>&lt;C-X&gt;&lt;C-F&gt;</code></td><td>Auto-completion of path in insert mode</td></tr></tbody></table>

{: .-shortcuts}

### Text alignment

    :center [width]
    :right [width]
    :left

See `:help formatting`

### Calculator

<table><thead><tr class="header"><th>Shortcut</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>&lt;C-R&gt;=128/2</code></td><td>Shows the result of the division : ‘64’</td></tr></tbody></table>

Do this in insert mode.

### Exiting with an error

    :cq
    :cquit

Works like `:qa`, but throws an error. Great for aborting Git commands.

### Spell checking

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th>Shortcut</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>:set spell spelllang=en_us</code></td><td>Turn on US English spell checking</td></tr><tr class="even"><td><code>]s</code></td><td>Move to next misspelled word after the cursor</td></tr><tr class="odd"><td><code>[s</code></td><td>Move to previous misspelled word before the cursor</td></tr><tr class="even"><td><code>z=</code></td><td>Suggest spellings for the word under/after the cursor</td></tr><tr class="odd"><td><code>zg</code></td><td>Add word to spell list</td></tr><tr class="even"><td><code>zw</code></td><td>Mark word as bad/mispelling</td></tr><tr class="odd"><td><code>zu</code> / <code>C-X (Insert Mode)</code></td><td>Suggest words for bad word under cursor from spellfile</td></tr></tbody></table>

{: .-shortcuts}

See `:help spell`

Also see
--------

-   [Vim cheatsheet](https://vim.rtorr.com/) *(vim.rotrr.com)*
-   [Vim documentation](http://vimdoc.sourceforge.net/htmldoc/) *(vimdoc.sourceforge.net)*
-   [Interactive Vim tutorial](http://openvim.com/) *(openvim.com)*
