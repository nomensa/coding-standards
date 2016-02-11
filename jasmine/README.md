# Jasmine


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
