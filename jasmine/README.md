# Jasmine

## Clean test markup

- Markup used to initiate a plugin should be kept clean of HTML comments.
A HTML comment can be easily introduced by copying the markup generated in the source code of the plugin.
Logic errors can occur if markup contains the trailing HTML comment, as jQuery will count this as a second element.

    ```javascript
    // bad
    var markup = '<div class="component"> </div> <!-- .component -->';

    // good
    var markup = '<div class="component"> </div>';
    ```