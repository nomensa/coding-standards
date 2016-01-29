# jQuery

## Abstracting functions

- Functions should be in a position that they are in a position to be reused.

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