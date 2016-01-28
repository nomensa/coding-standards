# HTML

Our standard for writing HTML.


## Table of Contents

- [Comments](#comments)
- [Character encoding](#character-encoding)
- [URLs](#urls)


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

## Conditional statements

- Conditional statements that check for IE versions should be wrapped around the 'html' element.

    ```html
    <!-- bad -->
    <!--[if IE 6]> <body> <!--![endif]-->

    <!-- good -->
    <!--[if IE 6]> <html> <!--![endif]-->
    ```