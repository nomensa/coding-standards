# SCSS / CSS

Our standard for writing SCSS and CSS.


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

    // bad
    // This is a very long comment that might span multiple lines and therefore might want to span across two lines

    // good
    // This is a very long comment that might span multiple lines and
    // therefore might want to span across two lines
    ```