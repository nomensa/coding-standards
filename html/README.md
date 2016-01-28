# HTML

## JavaScript hooks

- JavaScript hooks should be written as data-js="[component]".

    ```html
    <!-- bad -->
    <div class="js-accordion">

    <!-- bad -->
    <div data-js-accordion>

    <!-- good -->
    <div data-js="accordion clickable">
    ```
