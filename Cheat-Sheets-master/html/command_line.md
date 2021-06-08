;

List (ls)
---------

    ls [options] [paths]

### Format

<table><thead><tr class="header"><th>Switch</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>-1</code></td><td>One entry per line</td></tr><tr class="even"><td><code>-l</code></td><td>Long view</td></tr><tr class="odd"><td><code>-o</code></td><td>Long view (without groups)</td></tr><tr class="even"><td><code>-C</code></td><td>Multicolumn (sorted horizontally)</td></tr><tr class="odd"><td><code>-x</code></td><td>Multicolumn (sorted vertically)</td></tr><tr class="even"><td>—</td><td></td></tr><tr class="odd"><td><code>-F</code></td><td>Add / after directories</td></tr><tr class="even"><td><code>-G</code></td><td>Color</td></tr></tbody></table>

{:.shortcuts}

### Options

`-R` | Recurse |  
`-a` | Include hidden (dotfiles) |  
`-A` | Include hidden (but not . and ..) |

{:.shortcuts}

### Sorting

<table><thead><tr class="header"><th>Switch</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>-r</code></td><td>reverse order</td></tr><tr class="even"><td><code>-S</code></td><td>sort by size</td></tr><tr class="odd"><td><code>-t</code></td><td>sort by time modified</td></tr><tr class="even"><td><code>-u</code></td><td>sort by time accessed</td></tr><tr class="odd"><td><code>-U</code></td><td>sort by time created</td></tr><tr class="even"><td><code>-c</code></td><td>sort by time status was changed</td></tr><tr class="odd"><td>—</td><td></td></tr><tr class="even"><td><code>-h</code></td><td>Human-readable size (3k)</td></tr></tbody></table>

{:.shortcuts}

  

Tail
----

    tail [-F | -f | -r] [-bN | -cN | -nN] [file ...]

### Modes

`-f` | follow |  
`-F` | follow by filename (accounts for log rotation) |  
`-r` | Reverse order |

{:.shortcuts}

### Options

`-bN` | N\*512 bytes |  
`-cN` | N bytes |  
`-nN` | N lines |  
`+N` | Start from line N |

{:.shortcuts}

  

Sudo
----

    sudo [options] <command>

### Listing

`-l` | List allowed commands |

{:.shortcuts}

### Options

`-A` | Use $SUDO\_ASKPASS |  
`-b` | Run in background |  
`-E` | Preserve environment |  
`-H` | use target’s $HOME |  
`-n` | Don’t prompt for password |  
`-P` | Preserve group vector |  
`-S` | Read password from stdin |

{:.shortcuts}

### File descriptors

`-C fd` | Close all open file descriptors |

{:.shortcuts}

### Prompt

`-p prompt` | Custom prompt (-p “%p password:”) |

{:.shortcuts}

### Interactive

<table><thead><tr class="header"><th>Switch</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>-i [cmd]</code></td><td>Interactive shell without variables</td></tr><tr class="even"><td><code>-s [cmd]</code></td><td>Interactive shell</td></tr><tr class="odd"><td>—-</td><td></td></tr><tr class="even"><td><code>-u user</code></td><td>run as this user</td></tr><tr class="odd"><td><code>-g group</code></td><td>run as this group</td></tr></tbody></table>

{:.shortcuts}

### Timestamp

`-v` | revalidate timestamp for 5 mins |  
`-k` | invalidate timestamp |  
`-K` | just like -k |

{:.shortcuts}

  

wc (Word count)
---------------

    ... | wc [options]

`-c` | Bytes |  
`-l` | Lines |  
`-m` | Characters (incl multi-byte) |  
`-w` | Words |

{:.shortcuts}

  

Search-and-replace in all files
-------------------------------

    perl -p -i -e 's/hello/HELLO/g' **/*

  

Grep
----

    grep [options] [pattern] [file ...]

### Options

<table><thead><tr class="header"><th>Switch</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>-A num</code></td><td>Print <code>num</code> lines of training context</td></tr><tr class="even"><td>—-</td><td></td></tr><tr class="odd"><td><code>-G</code></td><td>–basic-regexp (default)</td></tr><tr class="even"><td><code>-E</code></td><td>–extended-regexp</td></tr><tr class="odd"><td><code>-P</code></td><td>–perl-regexp</td></tr><tr class="even"><td>—-</td><td></td></tr><tr class="odd"><td><code>-f file</code></td><td>–file (Get patterns for file)</td></tr><tr class="even"><td><code>-F</code></td><td>–fixed-strings</td></tr><tr class="odd"><td>—-</td><td></td></tr><tr class="even"><td><code>-h</code></td><td>–no-filename</td></tr><tr class="odd"><td><code>-H</code></td><td>–with-filename</td></tr><tr class="even"><td>—-</td><td></td></tr><tr class="odd"><td><code>-l</code></td><td>–files-with-matches (just print filenames)</td></tr><tr class="even"><td><code>-L</code></td><td>–files-without-match</td></tr><tr class="odd"><td>—-</td><td></td></tr><tr class="even"><td><code>-r, -R</code></td><td>–recursive</td></tr><tr class="odd"><td><code>-v</code></td><td>–invert-match</td></tr><tr class="even"><td><code>-i</code></td><td>–ignore-case</td></tr></tbody></table>

{:.shortcuts}

### Synonyms

    egrep  =>  grep -E
    fgrep  =>  grep -F
