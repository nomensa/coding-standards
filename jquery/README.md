# jQuery

Our standard for writing jQuery.

## Table of contents

- [Chaining](#chaining)
- [Plugins](#plugins)


## Chaining

- Chaining should be used when calling consecutive methods on the same object and each chain should be written on a new line for consistency. The chain should be indented one level.

    ```javascript
    // bad
    var nomensa = $('.nomensa');

    nomensa.addClass('foo');
    nomensa.show();

    // good
    var nomensa = $('.nomensa');

    nomensa
        .addClass('foo')
        .show();
    ```

    ### Further reading

    [jQuery.org: Chained method calls](https://contribute.jquery.org/style-guide/js/#chained-method-calls)


## Plugins

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
