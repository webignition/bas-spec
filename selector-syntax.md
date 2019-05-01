# Selector Syntax

A `selector` is a string identifying one or more page elements and is used in conjunction with the 
`click`,  `set`, `submit` and `wait-for` actions and with [assertion instructions](/assertion-syntax.md).

## Syntax

`"{css-selector-or-xpath-query}"[:{position}]`

- `css-selector-or-xpath-query`: any valid CSS selector or XPath query
- `position`: optional, the position with a set of elements if the selector matches more than one element

## Examples

- `"#element-id"`: a CSS selector matching against the element `id` attribute
- `"//*[@id="element-id"]`: an XPath query matching against the element `id` attribute
- `".listed-item":1`: a CSS selector matching all elements with the `listed-item` class name, fetching the first item in the list
- `".listed-item":3`: a CSS selector matching all elements with the `listed-item` class name, fetching the third item in the list
- `".listed-item":first`: special position keyword `first` is equivalent to `:1`
- `".listed-item":last`: special position keyword `last` fetches the last matching item
