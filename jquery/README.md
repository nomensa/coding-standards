# jQuery

## Chaining

- Chaining should be used when calling consecutive methods on the same object.

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

- Each chain should be written on a new line for consistency. The chain should be indented by one level.

    ```javascript
    // bad
    var nomensa = $('.nomensa');

    nomensa.addClass('foo').show();

    // good
    var nomensa = $('.nomensa');

    nomensa
        .addClass('foo')
        .show();
    ```

    ### Further reading

    [jQuery.org: Chained method calls](https://contribute.jquery.org/style-guide/js/#chained-method-calls)