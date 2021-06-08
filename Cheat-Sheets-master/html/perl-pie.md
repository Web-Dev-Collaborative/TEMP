;

### Search and replace

    perl -p -i -e 's/hello/hola/g' *.txt

### Back-referencing

Use `\1` et al.

    # '@include align-items(center);' => 'align-items: center;'
    perl -p -i -e "s/\@include (align-items)\((.*)\);/\1: \2;/g"
