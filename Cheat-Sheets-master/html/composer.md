;

All composer commands, depending on your install, may need to use `php composer.phar` in the install folder for composer, instead of plain `composer`.

### Installing dependencies

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th>Command</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>composer install</code></td><td>Downloads and installs all the libraries and dependencies outlined in the <code>composer.lock</code> file. If the file does not exist it will look for composer.json and do the same, creating a <code>composer.lock</code> file.</td></tr><tr class="even"><td>—</td><td>—</td></tr><tr class="odd"><td><code>composer install --dry-run</code></td><td>Simulates the install without installing anything</td></tr></tbody></table>

This command doesn’t change any file. If `composer.lock` is not present, it will create it.

`composer.lock` **should always** be committed to the repository. It has all the information needed to bring the local dependencies to the last committed state. If that file is modified on the repository, you will need to run `composer install` again after fetching the changes to update your local dependencies to those on that file.

### Updating packages

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th>Command</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>composer update</code></td><td>Updates all packages</td></tr><tr class="even"><td><code>composer update --with-dependencies</code></td><td>Updates all packages and its dependencies</td></tr><tr class="odd"><td>—</td><td>—</td></tr><tr class="even"><td><code>composer update vendor/package</code></td><td>Updates a certain <code>package</code> from <code>vendor</code></td></tr><tr class="odd"><td><code>composer update vendor/*</code></td><td>Updates all packages from <code>vendor</code></td></tr><tr class="even"><td><code>composer update --lock</code></td><td>Updates <code>composer.lock</code> hash without updating any packages</td></tr></tbody></table>

This command changes only the `composer.lock` file.

### Updating autoloader

<table><thead><tr class="header"><th>Command</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>composer dumpautoload -o</code></td><td>Generates optimized autoload files</td></tr></tbody></table>

### Adding packages

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th>Command</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>composer require vendor/package</code>.</td><td>Adds <code>package</code> from <code>vendor</code> to composer.json’s <code>require</code> section and installs it</td></tr><tr class="even"><td>—</td><td>—</td></tr><tr class="odd"><td><code>composer require vendor/package --dev</code></td><td>Adds <code>package</code> from <code>vendor</code> to composer.json’s <code>require-dev</code> section and installs it.</td></tr></tbody></table>

This command changes both the `composer.json` and `composer.lock` files.

### Removing packages

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th>Command</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>composer remove vendor/package</code></td><td>Removes <code>vendor/package</code> from composer.json and uninstalls it</td></tr></tbody></table>

This command changes both the `composer.json` and `composer.lock` files.
