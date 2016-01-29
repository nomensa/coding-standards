# jQuery

## Global variables

- Plugins should not create global variables. This excludes third party libraries.

    ```javascript
    // bad
    var plugin = 'nomensa';

    (function ($, window, document, undefined) {
        // ...stuff...
    });

    // good

    (function ($, window, document, undefined) {
        var plugin = 'nomensa';
        // ...stuff...
    });
    ```