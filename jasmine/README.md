# Jasmine

## Organising tests

- The ```describe``` function.

    The ```describe``` function is there to help give context to tests.
    Even if there is only one test, that test should sit inside a 'describe' function.
    Some advantages of the ```describe``` function are:
    - Prevents repetition of the same description for related tests;
    - Increases readability as tests are visually grouped together;
    - Helps debugging processes. A single 'describe' suite can be disabled and all tests inside that will inherit that disabled state.

    ```javascript
    // bad
    it('should initialise the plugin');

    it('should protect against multiple instantiations');

    // good
    describe('plugin initialisation', function() {
        it('should initialise the plugin');

        it('should protect against multiple instantiations');
    });
    ```

## Before and after each

- Watch out for bottle-necks when using ```beforeEach``` and ```afterEach```
    The before and after functions are great for re-using code and inheriting context, but they should be used with caution.
    Heavy use of the beforeEach and afterEach functions can decrease readability and introduce logic errors.

    A typical example of this would be to use the ```beforEach``` function to initialise a plugin:
        ```javascript
            // bad
            beforeEach(function() {
                var testElement = $('.markup');
                testElement.plugin();
            });

            it('should do foo');

            // ... Many lines later ...

            describe('options', function() {

                it('should run the callback', function() {
                    testElement.plugin({
                        callback: function() {
                            console.log('this will never run');
                        }
                    });
                });
            });

            // good
            beforeEach(function() {
                var testElement = $('.markup');
            });

            it('should do foo');

            // ... Many lines later ...

            describe('options', function() {

                it('should run the callback', function() {
                    testElement.plugin({
                        callback: function() {
                            console.log('this will run');
                        }
                    });
                });
            });
        ```
    In the *bad* example, we can recognise good and bad points.
    - (Good): The beforeEach function efficiently initiates the plugin for each test condition.
    - (Bad): Current and future developers will have to remember to check the beforeEach function for each condition.

## Clean test markup

- Markup used to initiate a plugin should be kept clean of HTML comments.
A HTML comment can be easily introduced by copying the markup generated in the source code of the plugin.
Logic errors can occur if markup contains the trailing HTML comment, as jQuery will count this as a second element.

    ```javascript
    // bad
    var markup = '<div class="component"> </div> <!-- .component -->';

    // good
    var markup = '<div class="component"> </div>';
    ```
