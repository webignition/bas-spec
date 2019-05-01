# Test Syntax
A test is comprised of two parts:
 - a series of [actions](/action-syntax.md) to be performed in order to get the page under test into the correct state
 - a set of [assertions](/assertion-syntax.md) to be evaluated in order to determine that the correct state has been achieved
 
## Format Definitions

Examples use special tokens to denote non-literal text. 

- `{variable-placeholder}`: indicates where a variable value is to be used
- `[...]`: square brackets denote optional syntax that can be omitted

## Syntax

A test is a YAML object with `actions` and `assertions` properties.

The `actions` property is a list of [actions](/action-syntax.md).
The `assertions` property is a list of [assertions](/assertion-syntax.md).

All actions take the form of a verb followed by zero or more arguments and keywords.

Action arguments can be represented by placeholders. The passing of values to replace placeholders is yet to be documented.

```yaml
actions:
  - ...
  - ...
  - ...
    
assertions:    
  - ...
  - ...
  - ...
```

## Examples

### Without placeholders

```yaml
actions:
  - open "https://example.com"

assertions:
  - "title" is "Example Domain"
```

### With placeholders

```yaml
actions:
  - open {{ url }}

assertions:
  - {{ title_selector }} is {{ expected_title }}
```