;

### Expressions

<table><thead><tr class="header"><th>Expression</th><th>Example</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>!!</code></td><td><code>sudo !!</code></td><td>Last command (<code>sudo !!</code>)</td></tr><tr class="even"><td>—</td><td>—</td><td>—</td></tr><tr class="odd"><td><code>!*</code></td><td><code>vim !*</code></td><td>Last command’s parameters (<code>vim !*</code>)</td></tr><tr class="even"><td><code>!^</code></td><td></td><td>Last command’s first parameter</td></tr><tr class="odd"><td><code>!$</code></td><td></td><td>Last command’s last parameter</td></tr><tr class="even"><td>—</td><td>—</td><td>—</td></tr><tr class="odd"><td><code>!?ls</code> <code>&lt;tab&gt;</code></td><td><code>sudo !?mv</code> <code>&lt;tab&gt;</code></td><td>Command and params of last <code>ls</code> command</td></tr><tr class="even"><td><code>!?ls?:*</code> <code>&lt;tab&gt;</code></td><td></td><td>Params of last <code>ls</code> command</td></tr><tr class="odd"><td>—</td><td>—</td><td>—</td></tr><tr class="even"><td><code>*(m0)</code></td><td><code>rm *(m0)</code></td><td>Last modified today</td></tr><tr class="odd"><td><code>*(m-4)</code></td><td></td><td>Last modified &lt;4 days ago</td></tr></tbody></table>

{: .-headers}

### Change default shell

    chsh -s `which zsh`

### Process Substitution

<table style="width:99%;"><colgroup><col style="width: 33%" /><col style="width: 33%" /><col style="width: 33%" /></colgroup><thead><tr class="header"><th>Expression</th><th>Example</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>&lt;(COMMAND)</code></td><td><code>grep "needle" &lt;(curl "https://haystack.io")</code></td><td>Replace argument with <em>named pipe/FIFO</em> (read-only) with command output</td></tr><tr class="even"><td><code>=(COMMAND)</code></td><td><code>vim =(curl "https://haystack.io")</code></td><td>Replace argument with <em>file</em> (writable) containing command output</td></tr></tbody></table>

{: .-headers}

### Also see

-   [Bash cheatsheet](./bash)

Zsh is mostly compatible with Bash, so most everything in Bash’s cheatsheet also applies.
