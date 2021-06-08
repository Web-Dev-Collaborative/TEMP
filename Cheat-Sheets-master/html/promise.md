;

Based on the [Promise API reference](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) (mozilla.org). {:.brief-intro.center}

### Creating promises

    new Promise(function (ok, err) {
      doStuff(function () {
        if (success) { ok(); }
        else { err(); }
      });
    })

### Consuming promises

    promise
      .then(okFn, errFn)
      .catch(errFn)

### Multiple promises

    var promises = [
      promise1(), promise2(), ...
    ]

    // succeeds when all succeed
    Promise.all(promises)
      .then(function (results) {
      });

    // succeeds when one finishes first
    Promise.race(promises)
      .then(function (result) {
      });

### Converting other promises

    return Promise.resolve("result");
    return Promise.resolve(promise);
    return Promise.resolve(thenable);

    return Promise.reject("reason");

    Promise.resolve($.get('http://google.com'))
    .then(...)
