# Verification Syntax
A verification instruction checks whether a given assertion is correct.

## Format Definitions

Examples use special tokens to denote non-literal text. 

- `{variable-placeholder}`: indicates where a variable value is to be used
- `[...]`: square brackets denote optional syntax that can be omitted

## Instruction syntax

Verification instructions take the form of the `assert` action followed by a `selector`, a `comparison` and an
 optional `value`.

`assert {selector} {comparison} [{value}]`

## Arguments

**`selector`**

Any valid [`selector`](/selector-syntax.md).

**`comparison`**

One of:
- `is`
- `is-not`
- `includes`
- `excludes`
- `matches`

**`value`**:

Used with the `is`, `is-not`, `includes`, `excludes` and `matches` comparisons.

`is`, `is-not`, `includes` and `excludes` expect a string value.
`matches` expects a regular expression

## Comparisons

### is 

Checks if the value being compared equals a given value.

#### Syntax
`assert {selector} is {value}`

Everything after the `is` keyword (except the space after the keyword) is the value to be used.

#### Examples
- `assert "title" is Homepage`
- `assert "title" is "Homepage"` (double quotes are taken literally)
- `assert "a[href=/sign-in/"] is Sign in`

### is-not

Checks if the value being compared does not equal a given value.

#### Syntax
`assert {selector} is-not {value}`

Everything after the `is-not` keyword (except the space after the keyword) is the value to be used.

#### Examples
- `assert "title" is-not Account`
- `assert "a[href=/sign-in/"] is-not My Account`

### includes

Checks if the value being compared contains a given value.

#### Syntax
`assert {selector} includes {value}`

Everything after the `includes` keyword (except the space after the keyword) is the value to be used.

#### Examples
- `assert "title" includes account`

### excludes

Checks if the value being compared does not contain a given value.

#### Syntax
`assert {selector} excludes {value}`

Everything after the `excludes` keyword (except the space after the keyword) is the value to be used.

#### Examples
- `assert "title" excludes Homepage`

### exists

Checks if the element identified by the `selector` exists on the page.

#### Syntax
`assert {selector} exists`

#### Examples
- `assert "p.sign-in-warning" exists`

### not-exists

Checks if the element identified by the `selector` does not exist on the page.

#### Syntax
`assert {selector} not-exists`

#### Examples
- `assert "p.sign-in-warning" not-exists`

### is 

Checks if the value being compared matches a given regular expression.

#### Syntax
`assert {selector} matches {regex}`

Everything after the `matches` keyword (except the space after the keyword) is the regular expression to be used.

#### Examples
- `assert "title" matches /homepage$/i`
