;

Commands
--------

{: .-three-column}

### Common commands

<table><thead><tr class="header"><th>Command</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>pacman -Syu &lt;pkg&gt;</code></td><td>Install (and update package list)</td></tr><tr class="even"><td><code>pacman -S &lt;pkg&gt;</code></td><td>Install only</td></tr><tr class="odd"><td><code>pacman -Rsc &lt;pkg&gt;</code></td><td>Uninstall</td></tr><tr class="even"><td><code>pacman -Ss &lt;keywords&gt;</code></td><td>Search</td></tr><tr class="odd"><td><code>pacman -Syu</code></td><td>Upgrade everything</td></tr></tbody></table>

{: .-prime}

### Query

<table><thead><tr class="header"><th>Command</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>pacman -Qe</code></td><td>List explictly-installed packages</td></tr><tr class="even"><td>—</td><td>—</td></tr><tr class="odd"><td><code>pacman -Ql &lt;pkg&gt;</code></td><td>What files does this package have?</td></tr><tr class="even"><td><code>pacman -Qii &lt;pkg&gt;</code></td><td>List information on package</td></tr><tr class="odd"><td>—</td><td>—</td></tr><tr class="even"><td><code>pacman -Qo &lt;file&gt;</code></td><td>Who owns this file?</td></tr><tr class="odd"><td>—</td><td>—</td></tr><tr class="even"><td><code>pacman -Qs &lt;query&gt;</code></td><td>Search installed packages for keywords</td></tr></tbody></table>

### Orphans

<table><thead><tr class="header"><th>Command</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>pacman -Qdt</code></td><td>List unneeded packages</td></tr><tr class="even"><td><code>pacman -Rns $(pacman -Qdtq)</code></td><td>Uninstall unneeded packages</td></tr></tbody></table>

Avoid orphans by using `pacman -Rsc` to remove packages, which will remove unneeded dependencies.

### Other

<table><thead><tr class="header"><th>Command</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>pactree &lt;pkg&gt;</code></td><td>What does <em>pkg</em> depend on?</td></tr><tr class="even"><td><code>pactree -r &lt;pkg&gt;</code></td><td>What depends on <em>pkg</em>?</td></tr></tbody></table>

### References

-   [Pacman tips and tricks](https://wiki.archlinux.org/index.php/Pacman/Tips_and_tricks) *(wiki.archlinux.org)*
