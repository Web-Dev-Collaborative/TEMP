;

### Mounting a RAM drive

    $ mount -t tmpfs -o size=5G,nr_inodes=5k,mode=700 tmpfs /tmp

### Visudo

    sudo visudo

    username ALL=(ALL) NOPASSWD:/sbin/restart whatever

### Display the amount of available disk space

    df
    df -h   # human-readable format
    df -a   # all filesystems

### Display disk usage

    du
    du -hsx * | sort -rh | head -10    # largest 10 folders

### Answer yes in a bash script

    yes | /your/command
