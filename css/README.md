# CSS / SCSS

Our standard for writing CSS and SCSS.


## Table of Contents

- [CSS](#css)
 - [BEM class naming](#bem-class-naming)
- [SCSS](#scss)
 - [Comments](#comments)


## CSS

### BEM class naming

- Class naming should follow the hyphenated BEM (Block, Element, Modifier) format.

    #### Block

    A block is an independent entity, a "building block" of an application. Block names should be separated by single dashes.

    ```css
    /* bad */
    .block_name {} // underscore

    .blockname {} // no separater

    .blockName {} // camelCase

    /* good */
    .block-name {}
    ```

    #### Element

    An element is a part of a block that performs a certain function.

    ```css
    /* bad */
    .block-name-element {} // dash between block and element

    .block-name_element {} // single underscore

    .block-nameElement {} // camelCase

    /* good */
    .block-name__element {}
    ```

    #### Modifier & states

    A modifier is a property of a block or an element that alters its look or behavior. States of a block or element should be treated as a modifier.

    ```css
    /* bad */
    .block-name__element-modifier {} // single dash between element and modifier

    .block-name__element_modifier {} // underscore

    .block-name__elementModifier {} // camelCase

    /* good */
    .block-name__element--modifier {}

    .block-name__element--is-open {}
    ```

    #### Further reading

    - [Mindbemding](http://csswizardry.com/2013/01/mindbemding-getting-your-head-round-bem-syntax/)
    - [Battling BEM](https://medium.com/fed-or-dead/battling-bem-5-common-problems-and-how-to-avoid-them-5bbd23dee319#.o3bm1o3ni)

### Indentation

- Indented by 4 space characters.

    ```css
    /* bad */
    .block {
      z-index: 1;
    }

    /* good */
    .block {
        z-index: 1;
    }
    ```


### Selectors

- Attribute selectors should be escaped using apostrophes.

    ```scss
    /* bad */
    [aria-expanded=true] {
        /* stuff */
    }

    /* good */
    [aria-expanded='true'] {
        /* stuff */
    }
    ````

- Internet Explorer specific CSS should be prefixed with the 'ie[version]' class.

    ```scss
    /* bad */
    html>/**/body .block {
        /* stuff */
    }

    /* good */
    .ie8 .block {
        /* stuff */
    }
    ```

### Properties and Values

- Each property must be on its own line, indented at one level.

    ```css
    /* bad */
    .block { z-index: 1; }

    /* good */
    .block {
        z-index: 1;
    }
    ```

- A value must be separated with a space from the property colon.

    ```css
    /* bad */
    .block {
        z-index:1;
    }

    /* good */
    .block {
        z-index: 1;
    }
    ```

- Properties should be written as shorthand where possible.

    ```css
    /* bad */
    .block {
        margin-top: 100px;
        margin-right: 100px;
        margin-bottom: 100px;
        margin-left: 100px;
    }

    /* good */
    .block {
        margin: 100px;
    }
    ```

- Decimal values should not omit zeros.

    ```css
    /* bad */
    .block {
        opacity: .9;
    }

    /* good */
    .block {
        opacity: 0.9;
    }
    ```

- Properties should be sorted in alphabetical order.

    ```css
    /* bad */
    .block {
        position: absolute;
        left: -999em;
        top: 0;
    }

    /* good */
    .block {
        left: -999em;
        position: absolute;
        top: 0;
    }
    ```

- Strings should be escaped using single quotes.

    ```scss
    /* bad */
    .block {
        content: "";
    }

    /* good */
    .block {
        content: '';
    }
    ```

- There should not be a space between parenthesis.

    ```css
    /* bad */
    .block {
        background: url( 'path/to/image.png' );
    }

    /* good */
    .block {
        background: url('path/to/image.png');
    }
    ```

- URLs should not contain protocols or domain names and should always be enclosed within quotes.

    ```css
    /* bad */
    background: url(https://example.com/assets/image.png);

    /* good */
    background: url('assets/image.png');
    ```

- Do not use vendor-prefixes. They add extra bloat to your code and are subject to change from the browser vendors.

    ```css
    /* bad */
    -moz-border-radius: 4px;
    -webkit-border-radius: 4px;
    border-radius: 4px;

    /* good */
    border-radius: 4px;
    ```

- Do not use !important. It is usually indicative of a misunderstanding of CSS [specificity](https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity) and can lead to brittle code.

    ```css
    /* bad */
    .block {
        z-index: 1 !important;
    }
    ```

- Hex colour values should be written in shorthand and lowercase.

    ```css
    /* bad */
    .nomensa {
        color: red;
    }

    .nomensa {
        color: #ff0000;
    }

    .nomensa {
        color: #F00;
    }

    /* good */
    .nomensa {
        color: #f00;
    }
    ```

- RGB/A values should be separated by a spaces.

    ```css
    /* bad */
    .nomensa {
        background: rgba(0,0,0,0.5);
    }

    /* good */
    .nomensa {
        background: rgba(0, 0, 0, 0.5);
    }
    ```


## SCSS

### Comments

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

### Sizing

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

### Nesting depth

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
                        ...
                    }
                }
            }
        }
    }

    // good
    .block {

        &__heading-sub {
            ...
        }
    ```

### Extend and Include

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