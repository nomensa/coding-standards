# jQuery

## Type checks

- Checking for the type of string, number, boolean etc. should be consistent.

 - String:
    ```javascript
    typeof object === 'string'
    ```
 - Number:
    ```javascript
    typeof object === 'number'
    ```
 - Boolean:
    ```javascript
    typeof object === 'boolean'
    ```
 - Object:
    ```javascript
    typeof object === 'object'
    ```
 - Function:
    ```javascript
    jQuery.isFunction(object)
    ```
 - Array:
    ```javascript
    jQuery.isArray(object)
    ```
 - Element:
    ```javascript
     object.nodeType
    ```
 - Null:
    ```javascript
    object === null
    ```
 - Undefined:
    ```javascript
    typeof variable === 'undefined'
    ```

### Further reading
- [jQuery.org: Type checks](https://contribute.jquery.org/style-guide/js/#type-checks)