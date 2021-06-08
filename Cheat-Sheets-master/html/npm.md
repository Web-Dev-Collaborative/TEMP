;

### Package management

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th>Command</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>npm i</code></td><td>Alias for <code>npm install</code></td></tr><tr class="even"><td><code>npm install</code></td><td>Install everything in package.json</td></tr><tr class="odd"><td><code>npm install --production</code></td><td>Install everything in package.json, except devDependecies</td></tr><tr class="even"><td>—</td><td>—</td></tr><tr class="odd"><td><code>npm install lodash</code></td><td>Install a package</td></tr><tr class="even"><td><code>npm install --save-dev lodash</code></td><td>Install as devDependency</td></tr><tr class="odd"><td><code>npm install --save-exact lodash</code></td><td>Install with exact</td></tr></tbody></table>

`--save` is the default as of npm@5. Previously, using `npm install` without `--save` doesn’t update package.json.

### Install names

<table><thead><tr class="header"><th>Command</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>npm i sax</code></td><td>NPM package</td></tr><tr class="even"><td><code>npm i sax@latest</code></td><td>Specify tag <code>latest</code></td></tr><tr class="odd"><td><code>npm i sax@3.0.0</code></td><td>Specify version <code>3.0.0</code></td></tr><tr class="even"><td><code>npm i sax@"&gt;=1 &lt;2.0"</code></td><td>Specify version range</td></tr><tr class="odd"><td>—</td><td>—</td></tr><tr class="even"><td><code>npm i @org/sax</code></td><td>Scoped NPM package</td></tr><tr class="odd"><td>—</td><td>—</td></tr><tr class="even"><td><code>npm i user/repo</code></td><td>GitHub</td></tr><tr class="odd"><td><code>npm i user/repo#master</code></td><td>GitHub</td></tr><tr class="even"><td><code>npm i github:user/repo</code></td><td>GitHub</td></tr><tr class="odd"><td><code>npm i gitlab:user/repo</code></td><td>GitLab</td></tr><tr class="even"><td>—</td><td>—</td></tr><tr class="odd"><td><code>npm i /path/to/repo</code></td><td>Absolute path</td></tr><tr class="even"><td><code>npm i ./archive.tgz</code></td><td>Tarball</td></tr><tr class="odd"><td><code>npm i https://site.com/archive.tgz</code></td><td>Tarball via HTTP</td></tr></tbody></table>

### Listing

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th>Command</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>npm list</code></td><td>Lists the installed versions of all dependencies in this software</td></tr><tr class="even"><td><code>npm list -g --depth 0</code></td><td>Lists the installed versions of all globally installed packages</td></tr><tr class="odd"><td><code>npm view</code></td><td>Lists the latest versions of all dependencies in this software</td></tr><tr class="even"><td><code>npm outdated</code></td><td>Lists only the dependencies in this software which are outdated</td></tr></tbody></table>

### Updating

<table><thead><tr class="header"><th>Command</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>npm update</code></td><td>Update production packages</td></tr><tr class="even"><td><code>npm update --dev</code></td><td>Update dev packages</td></tr><tr class="odd"><td><code>npm update -g</code></td><td>Update global packages</td></tr><tr class="even"><td>—</td><td>—</td></tr><tr class="odd"><td><code>npm update lodash</code></td><td>Update a package</td></tr></tbody></table>

### Misc features

    # Add someone as an owner
    npm owner add USERNAME PACKAGENAME

    # list packages
    npm ls

    # Adds warning to those that install a package of old versions
    npm deprecate PACKAGE@"< 0.2.0" "critical bug fixed in v0.2.0"

    # update all packages, or selected packages
    npm update [-g] PACKAGE

    # Check for outdated packages
    npm outdated [PACKAGE]
