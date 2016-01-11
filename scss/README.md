# SCSS / CSS

Our standard for writing SCSS and CSS.


## Table of Contents

- [SCSS](#scss)
 - [Comments](comments)
- [CSS](css)


## SCSS

### Comments

- Single-line and multi-line comments in SCSS should use `//`. These comments will be removed when compiled to CSS.

    ```scss
    // bad
    /* this comment will get output the the uncompressed CSS */

    // good
    // this comment will NOT get output the the uncompressed CSS

    // bad
    // This is a very long comment that might span multiple lines and therefore might want to span across two lines

    // good
    // This is a very long comment that might span multiple lines and
    // therefore might want to span across two lines
    ```

## CSS