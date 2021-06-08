;

Options
-------

### Options

    -o <file>    # --output: write to file
    -u user:pass # --user: Authentication

    -v           # --verbose
    -vv          # Even more verbose
    -s           # --silent

    -i           # --include: Include the HTTP-header in the output
    -I           # --head: headers only

### Request

    -X POST          # --request
    -L               # follow link if page redirects 

### Data

    -d 'data'    # --data: HTTP post data, URL encoded (eg, status="Hello")
    -d @file     # --data via file
    -G           # --get: send -d data via get

### Headers

    -A <str>         # --user-agent
    -b name=val      # --cookie
    -b FILE          # --cookie
    -H "X-Foo: y"    # --header
    --compressed     # use deflate/gzip

### SSL

        --cacert <file>
        --capath <dir>

    -E, --cert <cert>     # --cert: Client cert file
        --cert-type       # der/pem/eng
    -k, --insecure        # for self-signed certs

Examples
--------

{: .-one-column}

    # Post data:
    curl -d password=x http://x.com/y

    # Auth/data:
    curl -u user:pass -d status="Hello" http://twitter.com/statuses/update.xml

    # multipart file upload
    curl -v -include --form key1=value1 --form upload=@localfilename URL
