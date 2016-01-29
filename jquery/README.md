# jQuery

## Efficient selectors

- Be specific with selectors to reduce the use of the Sizzle engine in jQuery.

    ```javascript
    // bad
    $('.nomensa ul li a')

    // good
    $('.nomensa ul a')
    ```

    ### Further reading
    - [jQuery.com: Avoid Excessive Specificity](http://learn.jquery.com/performance/optimize-selectors/#specificity)

- Wildcard or Universal selectors can be slow to match. Avoid using them.

    ```javascript
    // bad
    $('.nomensa *')

    // bad
    $('[aria-expanded]')

    // good
    $('.nomensa .button[aria-expanded]')
    ```

    ### Further reading
    - [jQuery.com: Avoid the Universal Selector](http://learn.jquery.com/performance/optimize-selectors/#avoid-the-universal-selectory)