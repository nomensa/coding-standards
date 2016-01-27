# HTML

## Attribute order

- Attributes should be ordered alphabetically.

    ```html
    <!-- bad -->
    <div id="nomensa" class="nomensa" aria-describedby="foo" />

    <!-- good -->
    <div aria-describedby="foo" class="nomensa" id="nomensa" />
    ```

- Attributes should use double quotes.

    ```html
    <!-- bad -->
    <div class='nomensa'>

    <!-- good -->
    <div class="nomensa">
    ```

- Attributes should be written in lower case.

    ```html
    <!-- bad -->
    <div CLASS='nomensa'>

    <!-- good -->
    <div class="nomensa">
    ```