# jQuery

## Abstracting functions

- Functions used within jQuery methods should be abstracted into one place.
There can be two advantages from this:
1. It encourages functions to be re-used without the burden of refactoring them;
2. Improves readability;
3. Easier to debug and maintain code.

    ```javascript
    // bad
    var link = $('.link'),
        button = $('.button');

    link.click(function() {
        // ...stuff...
    });

    button.click(function() {
        // ...the same stuff...
    });

    // good
    var link = $('.link'),
        button = $('.button'),
        event = function event() {
            // ...stuff...
        };

    link.click(event);
    button.click(event);
    ```

    ### Further reading

    - [jQuery: Beware Anonymous Functions](http://learn.jquery.com/code-organization/beware-anonymous-functions)