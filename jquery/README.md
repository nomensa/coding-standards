# jQuery

Our standard for writing jQuery.

## Table of contents

- [Type checks](#type-checks)
- [Chaining](#chaining)
- [Plugins](#plugins)
- [Efficient selectors](#efficient-selectors)
- [Absent elements](#absent-elements)
- [Caching in loops](#caching-in-loops)
- [Ajax](#ajax)


## Type checks

- Checking for the type of object using jQuery should be consistent. Additional type checks are available using [JavaScript](../javascript/#type-checks).

    ```javascript
    // Function
    jQuery.isFunction(object)

    // Array
    jQuery.isArray(object)
    ```

    ### Further reading
    - [jQuery.org: Type checks](https://contribute.jquery.org/style-guide/js/#type-checks)


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


## Absent elements

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


## Caching in loops

- Properties used in conditions for loops should be cached beforehand.

    ```javascript
        // bad
        var links = $('.nomensa a');

        for (var i = 0; i < links.length; i++) {
            // ...stuff...
        }

        // good
        var linksCount = $('.nomensa a').length;

        for (var i = 0; i < linksCount; i++) {
            // ...stuff...
        }
    ```

    ### Further reading

    - [jQuery.com: Cache loop length](http://learn.jquery.com/performance/cache-loop-length/)


## Ajax

- Use the 'ajax' method instead of 'get', 'getJSON' and 'post'. The 'ajax' method can be used for all requests.

    ```javascript
        // bad
        $.get('path/to/file.html', callback());

        // good
        $.ajax({
            type: 'GET',
            url: 'path/to/file.html'
        });
    ```

    ### Further reading

    - [Envato Tuts: jQuery best practices](http://code.tutsplus.com/tutorials/14-helpful-jquery-tricks-notes-and-best-practices--net-14405)
