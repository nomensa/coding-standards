# HTML

Our standard for writing HTML.


## Table of Contents

- [Comments](#comments)
- [Character encoding](#character-encoding)
- [URLs](#urls)
- [Tags](#tags)


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


## Tags

- HTML tags should be self closed where appropriate.
The forward slash at the end of the tag is not necessary in HTML5, but it helps readability.

    ```html
    <!-- bad -->
    <link></link>

    <!-- good -->
    <link />
    ```

    ### Further reading

    - [Treehouse: Close tags in HTML5](http://blog.teamtreehouse.com/to-close-or-not-to-close-tags-in-html5)