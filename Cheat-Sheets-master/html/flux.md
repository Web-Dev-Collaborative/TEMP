;

Architecture
------------

-   **Dispatchers** receive *actions* that get dispatched to its listeners.

-   **Stores** are objects that store data, usually changed from a dispatcher listener.

-   **Views** are React components that listen to Store changes, or emit *actions* to the dispatcher.

------------------------------------------------------------------------

Dispatcher
----------

### Pub-sub

[A dispatcher](http://facebook.github.io/flux/docs/dispatcher.html) emits events (`.dispatch()`) to its listeners (`.register(fn)`).

    var Dispatcher = require('flux').Dispatcher;

    d = new Dispatcher();

    // send
    d.dispatch({ action: 'edit', ... };

    // receive
    token = d.register(function (payload) {
      payload.action === 'edit'
    })

### Ensuring proper order

With multiple listeners, you can ensure one is fired after another using `.waitFor()`.

    token1 = d.register(...);

    token2 = d.register(function (payload) {

      // ensure receiver 1 is fired before this
      d.waitFor([ token1 ]);
      
      // process here
    })

### Subclassing

[Object.assign](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/assign) is the preferred way to subclass Dispatcher (think `$.extend`).  
You can also make *action creators*, which are shortcuts for `dispatch()`.

    var Dispatcher = require('flux').Dispatcher;
    var assign = require('object-assign');

    var AppDispatcher = assign({}, Dispatcher.prototype, {

      // action creator
      handleViewAction(action) {
        this.dispatch({
          source: 'VIEW_ACTION',
          action: action
        })
      } 

    })

------------------------------------------------------------------------

Stores
------

### Plain objects

Stores are just like objects.

    var TodoStore = { list: [] };

### Events

Sometimes they’re eventemitters, too. Usually it’s used to emit `change` events for views to pick up.

    var TodoStore = assign({}, EventEmitter.prototype, {
      ...
    });

    TodoStore.emit('change');
    TodoStore.on('change', function () { ... });

### Model logic

Logic can sometimes belong in stores.

    {
      isAllActive() {
        return this.list.every(item => item.active);
      }
    }

------------------------------------------------------------------------

Stores and dispatchers
----------------------

### Instantiate

Make a Dispatcher and Stores.

    d = new Dispatcher();
    TabStore = { tab: 'home' };

### Updating data

Dispatch events to alter the store.

    d.dispatch({ action: 'tab.change', tab: 'timeline' });

    d.register(function (data) {
      if (data.action === 'tab.change') {
        TabStore.tab = data.tab;
      }
    });

------------------------------------------------------------------------

With Views
----------

### Listen to dispatchers

Views (React Components) can listen to Dispatchers.

    var TodoApp = React.createClass({

      componentDidMount() {
        this.token = AppDispatcher.register((payload) => {
          switch (payload.action) {
            case 'tab.change':
              this.render();
              // ...
          }
        });
      },
      
      componentDidUnmount() {
        AppDispatcher.unregister(this.token);
      }
      
    });

### Listen to Stores

Or to Stores’s `change` events.

    {
      componentDidMount() {
        TodoStore.on('change', this.onChange);
      },
      
      componentDidUnmount() {
        TodoState.removeListener('change', this.onChange);
      },
      
      onChange(data) {
        // ...
      }
    }

------------------------------------------------------------------------

### Also see

-   [Dispatcher API](http://facebook.github.io/flux/docs/dispatcher.html)
-   [React cheatsheet](react.html)
-   [Dispatcher.js source](https://github.com/facebook/flux/blob/master/src/Dispatcher.js)
-   [Flux-todomvc explanation](https://github.com/facebook/flux/tree/master/examples/flux-todomvc)
