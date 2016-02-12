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