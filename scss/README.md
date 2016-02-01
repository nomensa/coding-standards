# SCSS

Our standard for writing SCSS.


## Table of Contents

- [Comments](#comments)
- [Sizing](#sizing)
- [Nesting depth](#nesting-depth)
- [Extend and Include](#extend-and-include)


## Comments

- Single-line and multi-line comments in SCSS should use `//`. These comments will be removed when compiled to CSS.

    ```scss
    // bad
    /* this comment will get output the the uncompressed CSS */

    // good
    // this comment will NOT get output the the uncompressed CSS

    // also good
    // This is a very long comment that might span multiple lines and
    // therefore might want to span across two lines
    ```


## Sizing

- Where possible, sizes should use the 'pxtoem' or 'pxtopercent' functions - especially for font sizes.

    ```scss
    // bad
    .block {
        font-size: 12px;
        margin: 10px;
    }

    // good
    .block {
        font-size: pxtopercent(30);
        margin: pxtoem(1);
    }
    ```

    #### Further reading

    - [Nomensa: Text resizing tips](http://www.nomensa.com/blog/2013/text-resizing-tips)


## Nesting depth

- Nested styles must not exceed 4 levels.

    ```scss
    // bad
    .block {

        .block__element {
            ...

            .block__title {
                ...

                .block__title-heading {
                    ...

                    .block__heading-sub {
                        // ...stuff...
                    }
                }
            }
        }
    }

    // good
    .block {

        &__heading-sub {
            ...// ...stuff...
        }
    ```


## Extend and Include

- `@extend` rules should be positioned at the top of the style.

    ```scss
    // bad
    .block {
        // ...stuff...
        @extend .another-class;
    }

    // good
    .block {
        @extend .another-class;
        // ...stuff...
    }
    ```

- `@include` rules should be positioned at the top of the style but below `@extend` rules.

    ```scss
    // bad
    .block {
        @include opacity(1);
        @extend .another-class;
        // ...stuff...
    }

    // good
    .block {
        @extend .another-class;
        @include opacity(1);
        // ...stuff...
    }
    ```

- `@includes` with inner `@content` often involve `@media` rules that rely on the cascade or nested rule sets and therefore should be included after regular properties. `@include` rules that are positioned below styles should be separated by a new line.

    ```scss
    // bad
    .block {
        @include opacity(1);
        @extend .another-class;
        // ...stuff...
        @include breakpoint($mobile) {
            // ...stuff...
        }
    }

    // good
    .block {
        @extend .another-class;
        @include opacity(1);
        // ...stuff...

        @include breakpoint($tablet) {
            // ...stuff...
        }
    }
    ```