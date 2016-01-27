# JavaScript

Our standard for writing JavaScript.


## Table of Contents

- [Comments](comments)
- [Variables](variables)
- [Strict mode](strict mode)
- [Strings](strings)
- [Functions](functions)
- [Statements](statements)
- [New instances](new instances)


## Comments

- Single-line comments should use `//`. Place single line comments on a newline above the subject of the comment. Put an empty line before the comment unless it's on the first line of a block.

    ```javascript
    // bad
    const active = true;  // is current tab

    // good
    // is current tab
    const active = true;

    // bad
    function getType() {
      console.log('fetching type...');
      // set the default type to 'no type'
      const type = this._type || 'no type';

      return type;
    }

    // good
    function getType() {
      console.log('fetching type...');

      // set the default type to 'no type'
      const type = this._type || 'no type';

      return type;
    }

    // also good
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

## Variables

- Variables should always be declared at the top of functions.

    ```javascript
    // bad
    function foo() {
        var foo = 1;

        foo.onclick = function () {
            // ...stuff...
        }
    }

    // good
    function foo() {
        var foo = 1,
            baz = 2;

        foo.onclick = function () {
            // ...stuff...
        }
    }
    ```

- Variable names should be camelcased

    ```javascript
    // bad
    var foo_and_bar;
    // bad
    var foo-and-bar;

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

## Strings

- Strings should be escaped using the apostrophe character

    ```javascript
    // bad
    var foo = "foo";

    // good
    var foo = 'foo';

## Functions

- There shall be no space between the left and right bracket characters.

    ```javascript
    // bad
    function foo( bar ) {}

    // good
    function foo(bar) {}
    ```

- *Default*: There shall be no space from the function name and left bracket character.

    ```javascript
    // bad
    function foo (bar) {}

    // good
    function foo(bar) {}
    ```

- *Anonymous function*: There shall be one space from the function name and left bracket character.

    ```javascript
    // bad
    fooElement.onclick = function() {}

    // good
    fooElement.onclick = function () {}
    ```

- Variables that are passed to and from functions should be descriptive.

    ```javascript
    // bad
    fooElement.addEventListener('click', function(e){
        // ...stuff...
    });

    // good
    fooElement.addEventListener.click('click', function(event){
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

- New instances of arrays and objects should be written as shorthand:

    ```javascript
    // bad
    var foo = new Array(),
        bar = new Object;

    // good
    var foo = [],
        bar = {};
    ```