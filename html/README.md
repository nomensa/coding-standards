# HTML

## URLs

- URLs should not contain the protocol or domain name. URLs should be relative.

    ```html
    <!-- bad -->
    <img alt="" src="http://nomensa.com/path/to/image.png" />

    <!-- good -->
    <img alt="" src="/path/to/image.png" />
    ```