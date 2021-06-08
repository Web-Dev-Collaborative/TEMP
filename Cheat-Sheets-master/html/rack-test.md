;

### Methods

    get 'url'
    post 'url', 'name' => 'john'
    put
    patch
    delete
    options
    head

    authorize 'user', 'pass'
    env 'rack.session', csrf: 'token'
    header 'Content-Type', 'text/html'

See [rack/test.rb](https://github.com/brynary/rack-test/blob/master/lib/rack/test.rb).
