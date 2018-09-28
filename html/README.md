# HTML

Our standard for writing HTML.


## Table of Contents

- [Indentation](#indentation)
- [Conditional statements](#conditional-statements)
- [Character encoding](#character-encoding)
- [Comments](#comments)
- [Tags](#tags)
- [Attributes](#attributes)
- [Properties](#properties)
- [JavaScript hooks](#javascript-hooks)
- [URLs](#urls)


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
    ```


## Conditional statements

- Conditional statements that check for IE versions should be wrapped around the 'html' element.

    ```html
    <!-- good -->
    <!--[if IE 8]><html lang="en" class="ie8"><![endif]-->
    <!--[if IE 9]><html lang="en" class="ie9"><![endif]-->
    <!--[if (lt IE 8)|(gt IE 9)|!(IE)]><!--><html lang="en"><!--<![endif]-->
    ```

## Character encoding

- Pages should use the `utf-8` character encoding.

    ```html
    <!-- bad -->
    <meta charset="ISO-8859-1" />

    <!-- good -->
    <meta charset="utf-8" />
    ```


## Comments

- HTML comments should be used to indicate where a component ends.

    ```html
    <!-- bad -->
    <div class="component">

    </div>

    <!-- good -->
    <div class="component">

    </div><!-- .component -->
    ```


## Tags

- HTML tags should be self-closed. The forward slash at the end of the tag aids readability - even for HTML5 self-closing tags.

    ```html
    <!-- bad -->
    <link>
    <hr>
    <br>

    <!-- good -->
    <link />
    <hr />
    <br />
    ```

    ### Further reading

    - [Treehouse: Close tags in HTML5](http://blog.teamtreehouse.com/to-close-or-not-to-close-tags-in-html5)


## Attributes

- Attributes should be ordered alphabetically.

    ```html
    <!-- bad -->
    <div id="nomensa" class="nomensa" aria-describedby="foo">

    <!-- good -->
    <div aria-describedby="foo" class="nomensa" id="nomensa">
    ```

- Attributes should use double quotes.

    ```html
    <!-- bad -->
    <div class='nomensa'>

    <!-- good -->
    <div class="nomensa">
    ```

- Attributes should be written in lower case.

    ```html
    <!-- bad -->
    <div CLASS='nomensa'>

    <!-- good -->
    <div class="nomensa">
    ```

- Boolean attributes should not contain values.

    ```html
    <!-- bad -->
    <input checked="checked" type="checkbox" />

    <!-- good -->
    <input checked type="checkbox" />
    ```


## Properties

- Attribute and property should be ordered alphabetically.

    ```html
    <!-- bad -->
    <i class="icon icon--user icon--large" />

    <!-- good -->
    <i class="icon icon--large icon--user" />
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


## URLs

- URLs should not contain the protocol. URLs should be relative to avoid https security warnings.

    ```html
    <!-- bad -->
    <img alt="" src="http://example.com/path/to/image.png" />

    <!-- good -->
    <img alt="" src="//example.com/path/to/image.png" />
    ```