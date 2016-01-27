# CSS / SCSS

Our standard for writing CSS and SCSS.


## Table of Contents

- [CSS](css)
 - [BEM class naming](bem-class-naming)
- [SCSS](#scss)
 - [Comments](comments)


## CSS

### BEM class naming

- Class naming should follow the hyphenated BEM (Block, Element, Modifier) format.

    #### Block

    A block is an independent entity, a "building block" of an application. Block names should be separated by single dashes.

    ```scss
    // bad
    .block_name {} // underscore

    .blockname {} // no separater

    .blockName {} // camelCase

    // good
    .block-name {}
    ```

    #### Element

    An element is a part of a block that performs a certain function.

    ```scss
    // bad
    .block-name-element {} // dash between block and element

    .block-name_element {} // single underscore

    .block-nameElement {} // camelCase

    // good
    .block-name__element {}
    ```

    #### Modifier & states

    A modifier is a property of a block or an element that alters its look or behavior. States of a block or element should be treated as a modifier.

    ```scss
    // bad
    .block-name__element-modifier {} // single dash between element and modifier

    .block-name__element_modifier {} // underscore

    .block-name__elementModifier {} // camelCase

    // good
    .block-name__element--modifier {}

    .block-name__element--is-open {}
    ```

    #### Further reading

    - [Mindbemding](http://csswizardry.com/2013/01/mindbemding-getting-your-head-round-bem-syntax/)
    - [Battling BEM](https://medium.com/fed-or-dead/battling-bem-5-common-problems-and-how-to-avoid-them-5bbd23dee319#.o3bm1o3ni)


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

### Extend and Include

- Extend rules should be positioned at the top of the style.

    ```scss
    // bad
    .nomensa {
        // ...stuff...
        @extend .another-class;
    }

    // good
    .nomensa {
        @extend .another-class;

        // ...stuff...
    }
    ```

- Include rules should be positioned at the top of the style but below Exntend rules.
Include rules can be moved below styles if the cascaded or nested position benefits the rule.

    ```scss
    // bad
    .nomensa {
        @include opacity(1);
        @extend .another-class;
        // ...stuff...
    }

    // good
    .nomensa {
        @extend .another-class;
        @include opacity(1);
        // ...stuff...
    }
    ```
- Include rules that are positioned below styles should be separated by a new line

    ```scss
    // bad
    .nomensa {
        // ...stuff...
        @include opacity(1);
    }

    // good
    .nomensa {
        // ...stuff...

        @include opacity(1);
    }
    ```
