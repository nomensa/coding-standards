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


## Efficient selectors

- Be specific with selectors to reduce the use of the Sizzle engine in jQuery.

    ```javascript
    // bad
    $('.nomensa ul li a');

    // good
    $('.nomensa a');

    // better
    var nomensa = $('.nomensa');

    $(nomensa).find('a');
    ```

    ### Further reading
    - [jQuery.com: Avoid Excessive Specificity](http://learn.jquery.com/performance/optimize-selectors/#specificity)

- Wildcard or Universal selectors can be slow to match. Avoid using them.

    ```javascript
    // bad
    $('.nomensa > *');
    $('.nomensa > :radio');
    $('.nomensa > *:radio');

    // good
    $('.nomensa').children();
    $('.nomensa input:radio');
    ```

    ### Further reading

    - [jQuery.com: Avoid the Universal Selector](http://learn.jquery.com/performance/optimize-selectors/#avoid-the-universal-selectory)


## Assume absent elements

- Prevent code from executing if the object being manipulated does not exist.

    ```javascript
    // bad
    var nomensa = $('nomensa');

    nomensa.hide();

    // good
    var nomensa = $('nomensa');

    if (nomensa.length !== 0) {
        nomensa.hide();
    }
    ```

    ### Further reading

    - [jQuery.com: Absent Elements](http://learn.jquery.com/performance/dont-act-on-absent-elements/)
