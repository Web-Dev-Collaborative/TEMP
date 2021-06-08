;

Getting started
---------------

{: .-three-column}

### Quick start

{: .-prime}

#### app.js

{: .-file}

    const Camp = require('camp')
    const camp = Camp.start({ port: 1234 })

#### web/index.html

{: .-file}

    <!doctype html>
    <body>Hello world!</body>

Camp serves files in `web/` by default.

### Routes

#### Handles `/search?q=rainbows`

    camp.path('/search', (req, res) => {
      const q = res.query.q
      res.json({ results: ··· })
    })

{: data-line=“2”}

Also available: `camp.post`, `camp.get`.

### Templates

    const tpl = Camp.template('./templates/post.html')

    camp.path('/blog/:post.html', (req, res) => {
      res.template({
        text: 'Hello world'
      }, tpl)
    })

{: data-line=“1,4”}

See: [Templates](https://github.com/espadrine/sc/blob/master/doc/Readme.md#templates)

### Not found

    camp.notFound('/*.lol', (req, res) => {
      res.file('/404.html')
    })

{: data-line=“1”}

See: [Fall through](https://github.com/espadrine/sc/blob/master/doc/Readme.md#fall-through)

### Low level handler

    camp.handle((req, res, next) => {
      res.setHeader('X-Hello', 'world')
      next()
    })

{: data-line=“1”}

See: [Handlers](https://github.com/espadrine/sc/blob/master/doc/Readme.md#handlers)

Templates
---------

### Basic templates

    const tpl = Camp.template('/templates/post.html')

    camp.path('/blog/:post.html', (req, res) => {
      res.template({
        text: 'Hello world'
      }, tpl)
    })

{: data-line=“1,4,5,6”}

### Implicit templates

    camp.path('blog.html')

Uses `blog.html` as a template.

See: [Templates](https://github.com/espadrine/sc/blob/master/doc/Readme.md#templates)

Advanced features
-----------------

### Web sockets

    camp.ws('/path', (socket) => { ··· })

    camp.wsChannels[path]

    camp.wsBroadcast('/path', (req, res) => {
    })

Sorry I don’t completely understand this yet, but check it out in their docs.

See: [WebSocket](https://github.com/espadrine/sc/blob/master/doc/Readme.md#websocket)
