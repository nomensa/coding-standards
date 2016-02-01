# jQuery

Our standard for writing jQuery.


## Table of Contents

- [Abstracting functions](#abstracting-functions)


## Abstracting functions

- Functions should be in a reusable position.

    ```javascript
    // bad
    var link $('.link');

    link.click(function() {
        // ...stuff...
    });

    // good
    var link $('.link'),
        linkEvent = function () {
            // ...stuff...
        };

    link.click(function() {
        linkEvent;
    });
    ```