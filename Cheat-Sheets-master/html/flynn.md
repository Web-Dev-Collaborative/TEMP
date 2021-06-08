;

### General workflow

-   Start a flynn cluster (on amazon or vagrant)
-   `flynn cluster add` to add that cluster
-   `flynn create NAME` in your app
-   `git push flynn master` to deploy

### Creating a cluster (AWS)

    flynn install  # (provisions AWS EC2 stuff)
    flynn key add  # (adds your pubkey to AWS)

#### What it does

-   This creates `XXXX.flynnhub.com`
-   Dashboard in `dashboard.XXXX.flynnhub.com`
-   Use `flynn -a dashboard env get LOGIN_TOKEN` to get login token
-   Apps live in `APP.XXXX.flynnhub.com`

### Using a flynn cluster

Managed in `~/.flynnrc`: {: .-setup}

    flynn cluster
    flynn cluster add [-g githost] [-p pin] NAME URL KEY
    flynn cluster remove NAME
    flynn cluster default NAME # use this current

### Setting up a new app

    cd ~/project
    flynn create example # adds the `flynn` remote
    flynn route # prints http routes
    git push flynn master

Commands
--------

### Environment vars

    flynn env
    flynn env set FOO=bar BAZ=foobar
    flynn env unset FOO

### Scale

    flynn ps
    flynn scale web=3

### Logs

    flynn log
    flynn log flynn-d55c7a...

### Running commands

    flynn run rake db:migrate

### Manage routes

    flynn route
    flynn route add http example.com
    # then make a CNAME from example.com to myapp.xxxx.flynnhub.com

### More

    flynn ps
    flynn kill <job>

    flynn meta
    flynn meta set foo=baz

Also see
--------

-   [Flynn website](https://flynn.io/) *(flynn.io)*
