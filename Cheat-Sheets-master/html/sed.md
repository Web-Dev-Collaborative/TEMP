;

### In place replacements

#### In GNU sed: use `-i` without arg.

    sed -i -e 's/foo/bar/' example.md

#### In OSX, `-i ''` is required.

    sed -i '' -e 's/foo/bar/' example.md

### File regions

#### Print until a certain line is met

    sed '/begin api/q'

#### Print until a certain line is met, but not that line

    sed '/^# begin/,$d'

#### Print everything after a given line

    sed -n '/end api/,$p'
