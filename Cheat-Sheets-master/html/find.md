;

### Usage

{: .-prime}

    find <path> <conditions> <actions>

### Conditions

    -name "*.c"

    -user jonathan
    -nouser

    -type f            # File
    -type d            # Directory
    -type l            # Symlink

    -depth 2           # At least 3 levels deep
    -regex PATTERN

    -size 8            # Exactly 8 512-bit blocks 
    -size -128c        # Smaller than 128 bytes
    -size 1440k        # Exactly 1440KiB
    -size +10M         # Larger than 10MiB
    -size +2G          # Larger than 2GiB

    -newer   file.txt
    -newerm  file.txt        # modified newer than file.txt
    -newerX  file.txt        # [c]hange, [m]odified, [B]create
    -newerXt "1 hour ago"    # [t]imestamp

### Access time conditions

    -atime 0           # Last accessed between now and 24 hours ago
    -atime +0          # Accessed more than 24 hours ago
    -atime 1           # Accessed between 24 and 48 hours ago
    -atime +1          # Accessed more than 48 hours ago
    -atime -1          # Accessed less than 24 hours ago (same a 0)
    -ctime -6h30m      # File status changed within the last 6 hours and 30 minutes
    -mtime +1w         # Last modified more than 1 week ago

These conditions only work in MacOS and BSD-like systems (no GNU/Linux support).

### Condition flow

    \! -name "*.c"
    \( x -or y \)

### Actions

    -exec rm {} \;
    -print
    -delete

### Examples

    find . -name '*.jpg'
    find . -name '*.jpg' -exec rm {} \;

    find . -newerBt "24 hours ago"

    find . -type f -mtime +29 # find files modified more than 30 days ago
