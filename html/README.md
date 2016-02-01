# HTML

Our standard for writing HTML.


## Table of Contents

- [Comments](#comments)
- [Character encoding](#character-encoding)
- [URLs](#urls)
- [JavaScript hooks](#javascript-hooks)


## Commments

- HTML comments should be used to indicate where a component ends.

    ```html
    <!-- bad -->
    <div class="component">

    </div>

    <!-- good -->
    <div class="component">

    </div><!-- .component -->
    ```

## Character encoding

- Pages should use the `utf-8` character encoding.

    ```html
    <!-- bad -->
    <meta charset="ISO-8859-1">

    <!-- good -->
    <meta charset="utf-8">
    ```


## URLs

- URLs should not contain the protocol. URLs should be relative to avoid https security warnings.

    ```html
    <!-- bad -->
    <img alt="" src="http://example.com/path/to/image.png" />

    <!-- good -->
    <img alt="" src="//example.com/path/to/image.png" />
    ```


## JavaScript hooks

- JavaScript hooks should be written using a data-js attribute on the element.

    ```html
    <!-- bad -->
    <div class="js-accordion">

    <div data-js-accordion>

    <!-- good -->
    <div data-js="accordion">

    <div data-js="accordion clickable">
    ```

    ### Further reading

    - [data-js selectors](https://toddmotto.com/data-js-selectors-enhancing-html5-development-by-separating-css-from-javascript/)


## Indentation

- HTML should be indented by 4 spaces.

    ```html
    <!-- bad -->
    <ul>
      <li><!-- ...stuff... --></li>
    </ul>

    <!-- good -->
    <ul>
        <li><!-- ...stuff... --></li>
    </ul>


## Conditional statements

- Conditional statements that check for IE versions should be wrapped around the 'html' element.

    ```html
    <!-- good -->
    <!--[if IE 8]><html lang="en" class="ie8"><![endif]-->
    <!--[if IE 9]><html lang="en" class="ie9"><![endif]-->
    <!--[if (lt IE 8)|(gt IE 9)|!(IE)]><!--><html lang="en"><!--<![endif]-->
    ```