# Browser Properties

Properties of the browser can be accessed through the `browser` object and used directly within
[tests](/test-syntax.md) and [test suites](/test-suite-syntax.md).

## url

The current content of the browser address bar.

### Example Assertion Usage
```yaml
actions:
  - open "https://www.google.com"

assertions:
  - browser.url is "https://www.google.com"
```

## title

The page title (content of the `<title>` element).

### Example Assertion Usage
```yaml
actions:
  - open "https://www.google.com"

assertions:
  - browser.titke is "Google"
```
