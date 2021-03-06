# JavaScript

Our standard for writing JavaScript.


## Table of Contents

- [Modular pattern](#modular)
- [Comments](#comments)
- [Type checks](#type-checks)
- [Variables](#variables)
- [Strict mode](#strict-mode)
- [Strings](#strings)
- [Functions](#functions)
- [Statements](#statements)
- [New instances](#new-instances)
- [Conditional statements](#conditional-statements)
- [Use of CSS](#use-of-css)

## Modular
We encourage the Modular design pattern to help manage variable scope.

```javascript

    (function foo(localjQuery) {
        var $ = localjQuery;

    })(jQuery);
```


## Comments

- Single-line comments should use `//`. Place single line comments on a newline above the subject of the comment. Put an empty line before the comment unless it's on the first line of a block.

    ```javascript
    // bad
    const active = true;  // is current tab

    function getType() {
      console.log('fetching type...');
      // set the default type to 'no type'
      const type = this._type || 'no type';

      return type;
    }

    // good
    // is current tab
    const active = true;

    function getType() {
      console.log('fetching type...');

      // set the default type to 'no type'
      const type = this._type || 'no type';

      return type;
    }

    function getType() {
      // set the default type to 'no type'
      const type = this._type || 'no type';

      return type;
    }
    ```

- Multi-line comments should use `/** ... */`. Include a description, specify types and values for all parameters and return values.

    ```javascript
    // bad
    // make() returns a new element
    // based on the passed in tag name
    //
    // @param {String} tag
    // @return {Element} element
    function make(tag) {
        // ...stuff...
        return element;
    }

    // good
    /**
     * make() returns a new element
     * based on the passed in tag name
     *
     * @param {String} tag
     * @return {Element} element
     */
    function make(tag) {
        // ...stuff...
        return element;
    }
    ```


## Type checks

- Checking for the type of string, number, boolean etc. should be consistent. Additional type checks are available using [jQuery](../jquery/#type-checks).

    ```javascript
    // String
    typeof object === 'string'

    // Number
    typeof object === 'number'

    // Boolean
    typeof object === 'boolean'

    // Object
    typeof object === 'object'

    // Element
    object.nodeType

    // Null
    object === null

    // Undefined
    typeof variable === 'undefined'
    ```

    ### Further reading
    - [MDN typeof](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/typeof)
    - [Understanding JavaScript types](https://toddmotto.com/understanding-javascript-types-and-reliable-type-checking)


## Variables

- Variables should always be declared at the top of functions.

    ```javascript
    // bad
    function foo() {
        var foo = 1;

        foo.onclick = function () {
            // ...stuff...
        }

        var bar = 2;
    }

    // good
    function foo() {
        var foo = 1,
            bar = 2;

        foo.onclick = function () {
            // ...stuff...
        }
    }
    ```

- Variable names should be camelcased

    ```javascript
    // bad
    var foo_and_bar;
        foo-and-bar;

    // good
    var fooAndBar;
    ```

- Variable names should not contain dollar symbols

    ```javascript
    // bad
    var $element;

    // good
    var element;
    ```


## Strict mode

- Strict mode should be enabled at the top of each JS file.

    ```javascript
    // bad
    if (foo == bar) {}

    // good
    'use strict';

    if (foo === bar) {}
    ```

    ### Further reading

    - [Mozilla: Strict mode](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode)


## Strings

- Strings should be escaped using the apostrophe character

    ```javascript
    // bad
    var foo = "foo";

    // good
    var foo = 'foo';
    ```


## Functions

- There shall be no space between the left and right bracket characters.

    ```javascript
    // bad
    function foo( bar ) {}

    // good
    function foo(bar) {}
    ```

- There shall be no space from the function name and left bracket character.

    ```javascript
    // bad
    function foo (bar) {}

    fooElement.onclick = function () {}

    // good
    function foo(bar) {}

    fooElement.onclick = function() {}
    ```

- Variables that are passed to and from functions should be descriptive.

    ```javascript
    // bad
    fooElement.addEventListener('click', function(e) {
        // ...stuff...
    });

    // good
    fooElement.addEventListener('click', function(event) {
        // ...stuff...
    });
    ```

- Variables should not be assigned inside function declariations.

    ```javascript
    // bad
    function foo(var bar = 'foo') {}

    // good
    function foo() {
        var bar = 'foo'
    }
    ```

- Anonymous functions should be named for debugging reasons.

    ```javascript
    // bad
    var foo = (function() {});

    // good
    var foo = (function foo() {});
    ```

## Statements

- Statements should contain the same format as functions:

    ```javascript
    // bad
    if (foo){
        // ...stuff...
    } else{
        // ...stuff...
    }

    // good
    if (foo) {
        // ...stuff...
    } else {
        // ...stuff...
    }


    // bad
    for( var i = 1; i < 5; i++ ) {}

    // good
    for(var i = 1; i < 5; i++) {}


    // bad
    while( foo ) {}

    // good
    while(foo) {}


    // bad
    switch( foo ) {}

    // good
    switch(foo) {}
    ```


- `switch` Statements should indent each case

    ```javascript
    // bad
    switch(foo) {
        case bar:
        // ...stuff...
        break;

        case foo:
        // ...stuff...

        break
        }
    }

    // good
    switch(foo) {
        case bar:
            // ...stuff...
            break;

        case foo:
            // ...stuff...
            break
        }
    }
    ```


## New instances

- New instances of arrays and objects should be written as shorthand.

    ```javascript
    // bad
    var foo = new Array(),
        bar = new Object;

    // good
    var foo = [],
        bar = {};
    ```


## Conditional statements

- Conditional statements can become difficult to read when introducing the exclamation character. It is important to ensure that people can read conditional statements in a natural sentence.

    ```javascript
    // bad
    if (!condition === 0)

    // good
    if (condition !== 0)
    ```


## Use of CSS

- JavaScript should not contain CSS unless it is unavoidable.
CSS is effective, maintainable and readable inside stylesheets. It is neither of those inside JavaScript.

    ```javascript
    // bad
    $('.link').css('display', 'block');

    // Unavoidable
    $('.link').hide();

    // Good
    $('.link').toggleClass('hidden');
    ```

    ### Further reading

    - [W3C: Avoid mixing technologies](https://www.w3.org/wiki/JavaScript_best_practices#Avoid_mixing_with_other_technologies)
