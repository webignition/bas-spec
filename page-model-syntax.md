# Page Model Syntax

[Tests](/test-syntax.md) and [test suites](/test-suite-syntax.md) are executed within the context of a web page. 

A page model stores properties of a web page, avoiding the need to repetitively define such properties at the point
that they are needed.

## Syntax

A page model is a YAML document with `url` and `elements` properties.

The `url` property provides the URL for the web page.

The `elements` property is a collection mapping a convenience name to an [selector](/selector-syntax.md).

```yaml
url: {url}
elements:
  {element_name}: {selector}
```

## Example

```yaml
url: https://www.google.com
elements:
  title: "title"
  search_input: ".gLFyf.gsfi"
  search_button: ".FPdoLc.VlcLAe input[name=btnK]"
```

## Using a Page Model Within a Test Suite

Refer to the test suite example for [importing and using a page model](/test-suite-syntax.md#page-model-imported-into-the-test-suite).