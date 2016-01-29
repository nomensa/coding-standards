# CSS / SCSS

Our standard for writing CSS and SCSS.


## Table of Contents

- [CSS](#css)
 - [BEM class naming](#bem-class-naming)
 - [Indentation](#indentation)
 - [Brace alignment](#brace-alignment)
 - [Selectors](#selectors)
 - [Properties and Values](#properties-and-values)
 - [Container heights](#container-heights)
- [SCSS](#scss)
 - [Comments](#comments)
 - [Sizing](#sizing)
 - [Nesting depth](#nesting-depth)
 - [Extend and Include](#extend-and-include)


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

- Each level should be indented by 4 space characters.

    ```css
    /* bad */
    .block {
      /* stuff */
    }

    /* good */
    .block {
        /* stuff */
    }

    @media only screen and (min-device-width: 768px) {
        .block {
            /* stuff */
        }
    }
    ```

### Brace alignment

- The opening brace should be on the same line as the selector.

    ```css
    /* bad */
    .block
    {
        /* stuff */
    }

    /* good */
    .block {
        /* stuff */
    }
    ```

- The closing brace should be on a new line and at the start of the line.

    ```css
    // bad
    .block {
        /* stuff */ }

    // good
    .block {
        /* stuff */
    }
    ```


### Selectors

- Attribute selectors should be escaped using apostrophes.

    ```css
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

    ```css
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
    #### Further reading

    - [Smashing Magazine: When to use important](https://www.smashingmagazine.com/2010/11/the-important-css-declaration-how-and-when-to-use-it/)

- Hex colour values should be written in shorthand and lowercase.

    ```css
    /* bad */
    .block {
        color: red;
    }

    .block {
        color: #ff0000;
    }

    .block {
        color: #F00;
    }

    /* good */
    .block {
        color: #f00;
    }
    ```

- RGB/A values should be separated by a spaces.

    ```css
    /* bad */
    .block {
        background: rgba(0,0,0,0.5);
    }

    /* good */
    .block {
        background: rgba(0, 0, 0, 0.5);
    }
    ```

### Container heights

- `min-height` should be used instead of 'height' to avoid container overflow from being hidden.

    ```css
    /* bad */
    .block {
        height: 400px;
    }

    /* good */
    .block {
        min-height: 400px;
    }
    ```

    #### Further reading

    - [Nomensa: Text resizing tips](http://www.nomensa.com/blog/2013/text-resizing-tips)


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