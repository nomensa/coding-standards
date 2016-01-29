# jQuery

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

    [jQuery.com: Absent Elements](http://learn.jquery.com/performance/dont-act-on-absent-elements/)