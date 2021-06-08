;

Reference
---------

### Create

    $ pass init [-p] <gpg-id>
    $ pass git init
    $ pass git remote add origin <your.git:repository>
    $ pass git push -u --all

### Store

    $ pass insert [-m] twitter.com/rsc
    $ pass generate [-n] twitter.com/rsc length

### Retrieve

    $ pass ls twitter.com/
    $ pass show twitter.com/rsc
    $ pass -c twitter.com/rsc

### Search

    $ pass find twitter.com

### Management

    $ pass mv twitter.com twitter.com/rsc
    $ pass rm [-rf] twitter.com
    $ pass cp twitter.com/rsc twitter.com/ricosc

    $ pass edit twitter.com/rsc

### Synchronize

    $ pass git push
    $ pass git pull

References
----------

-   <a href="http://passwordstore.org" class="uri">http://passwordstore.org</a>
