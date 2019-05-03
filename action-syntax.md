# Action Syntax
A test starts with of a series of actions.

This document defines the syntax of a single action.

## Format Definitions

Examples use special tokens to denote non-literal text. 

- `{variable}`: indicates where a variable value is to be used
- `[...]`: square brackets denote optional syntax that can be omitted

## Syntax

All actions take the form of a verb followed by zero or more arguments and keywords.

`verb [arguments]`

## Verbs
- open
- click
- wait
- wait-for
- submit
- back
- forward
- reload
- set

### open

Visit a URL in the browser.

#### Syntax
`open {url} [in {browser}]`

#### Arguments
**`url`**

The URL to visit.
 
Single- or double-quoting is required if the URL contains either:
 - one or more whitespace characters
 - the "in" keyword preceded by a single space (" in")

**`browser`**

The browser to use. One of: `chrome`, `firefox`. Case-insensitive.

Optional, defaults to `chrome`.

#### Examples
- `open https://example.com`
- `open "https://example.com"`
- `open https://example.com in chrome`
- `open "https://example.com" in firefox`
- `open "https://example.com in chrome" in firefox`

### click

Perform a click action upon an element.

#### Syntax
`click {selector}`

#### Arguments
**`selector`**

Any valid [`selector`](/selector-syntax.md).

#### Examples
- `click ".btn.btn-sign-in"`
- `click ".listed-item":0`

### wait

Wait a specified number of seconds.

#### Syntax
`wait {number-of-seconds}`

#### Arguments
**`number-of-seconds`**

The number of seconds to wait. Must be an integer greater than zero.

#### Examples
- `wait 1`
- `wait 15`

### wait-for

Wait for an element to be rendered. Waits for up to 30 seconds.

#### Syntax
`wait-for {selector}`

#### Arguments
**`selector`**

Any valid [`selector`](/selector-syntax.md).

#### Examples
- `wait-for "#asychronously-loaded-content"`

### submit
Performs a submit action on a form.

#### Syntax
`submit {selector}`

#### Arguments
**`selector`**

Any valid [`selector`](/selector-syntax.md).

#### Examples
- `submit "#sign-in-form"`

### back
Move back one item in the current session history. Equivalent to clicking the browser back button.

#### Syntax
`back`

### forward
Move forward one item in the current session history. Equivalent to clicking the browser forward button.

#### Syntax
`forward`

### reload
Reload the current page. Equivalent to clicking the browser reload button.

#### Syntax
`reload`

### set
Set the value of an element. 

Most applicable to form field elements.

#### Syntax
`set {selector} to {value}`

Anything following the `to` keyword (except the space after the keyword) is the value to be used.

#### Arguments
**`selector`**

Any valid [`selector`](/selector-syntax.md).

**`value`**

The value to be set. Any string.

#### Examples

- `set "#sign-in-form .username" to user@example.com`
- `set "#sign-in-form .password" to "user@example.com"` (literally includes double quotes in the value)
