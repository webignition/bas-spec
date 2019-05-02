# Page Model Element Reference Syntax

A [page model](/page-model-syntax.md) can define convenience element names that map to [selectors](/selector-syntax.md).

Page model element names can be referenced [tests](/test-syntax.md) or [test suites](/test-suite-syntax.md) into which
the page model has been imported.

## Syntax

`{import_name}.elements.{element_name}`

## Example

```yaml
# page/google.com.yml
url: https://www.google.com
elements:
  search_input: ".gLFyf.gsfi"
  search_button: ".FPdoLc.VlcLAe input[name=btnK]"
```

```yaml
# test.yml
imports:
  pages:
    google_com: page/google.com.yml

actions:
  - set google_com.elements.search_input to "example"
  - click google_com.elements.search_button

assertions:
  - browser.title is "example - Google Search"
```

```yaml
# test-suite.yml
imports:
  pages:
    google_com: page/google.com.yml

"open https://www.google.com":
  actions:
    - open google_com

  assertions:
    - browser.title is "Google"

"query 'example'":
  actions:
    - set google_com.elements.search_input to "example"
    - click google_com.elements.search_button

  assertions:
    - browser.title is "example - Google Search"
```
