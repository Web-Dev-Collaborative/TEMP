;

### Revision ranges

    git log master             # branch
    git log origin/master      # branch, remote
    git log v1.0.0             # tag

    git log master develop

    git log v2.0..master       # reachable from *master* but not *v2.0*
    git log v2.0...master      # reachable from *master* and *v2.0*, but not both

See [gitrevisions](./git-revisions).

### Basic filters

    -n, --max-count=2
        --skip=2

        --since="1 week ago"
        --until="yesterday"

        --author="Rico"
        --committer="Rico"

### Search

        --grep="Merge pull request"   # in commit messages
        -S"console.log"               # in code
        -G"foo.*"                     # in code (regex)

        --invert-grep
        --all-match                   # AND in multi --grep

### Limiting

        --merges
        --no-merges

        --first-parent          # no stuff from merged branches

        --branches="feature/*"
        --tags="v*"
        --remotes="origin"

### Simplification

    git log -- app/file.rb          # only file
        --simplify-by-decoration    # tags and branches

### Ordering

        --date-order
        --author-date-order
        --topo-order              # "smart" ordering
        --reverse

### Formatting

        --abbrev-commit
        --oneline
        --graph

### Custom formats

        --pretty="format:%H"

See: [Git log format cheatsheet](./git-log-format)

Also see
--------

-   [Git log format cheatsheet](./git-log-format)
