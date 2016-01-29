# jQuery

## Caching in loops

- Properties used in conditions for loops should be cached beforehand.

    ```javascript
        // bad
        var links = $('.nomensa a');

        for (var i = 0; i < links.length; i++) {}

        // good
        var linksCount = $('.nomensa a').length;

        for (var i = 0; i < linksCount; i++) {}
    ```

    ### Further reading

    - [jQuery.com: Cache loop length](http://learn.jquery.com/performance/cache-loop-length/)