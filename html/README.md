# HTML


## Commments

- HTML comments should be used to indicate where a component ends.

    ```html
    <!-- bad -->
    <div class="component">

    </div>

    <!-- good -->
    <div class="component">

    </div><!-- .component -->


## Character encoding

- Pages should use the `utf-8` character encoding.

    ```html
        <!-- bad -->
        <meta charset="ISO-8859-1">

        <!-- good -->
        <meta charset="utf-8">
    ```