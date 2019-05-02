# Test Suite Syntax

A test suite is comprised of a series of [tests](/test-syntax.md).

Tests may be defined directly within a suite or may be imported.

## Syntax

A test suite is a YAML object with named properties where each named property defines the 
[actions](/action-syntax.md) and [assertions](/assertion-syntax.md) to be performed for a specific test.

```yaml
"{test_name}":
  actions:
    {actions}

  assertions:
    {assertions}
```

A test may be defined independently of the test suite and imported in one or more test suites.

Import names are user-defined. Import names for parameterised tests must not be `actions` or `assertions`.
Import paths are relative to the test suite.

```yaml
imports:
  tests:
    {import_name}: {import_path}

"first item to test":
  - {import_name}
```

A test suite may both define and import tests.

```yaml
imports:
  tests:
    {import_name}: {import_path}

"first item to test":
  - {import_name}

"{test_name}":
  actions:
    {actions}

  assertions:
    {assertions}
```

Imported tests that require parameters must have the parameter values passed at usage time.

```yaml
imports:
  tests:
    {import_name}: {import_path}

"first item to test":
  {import_name}:
    {parameter_name}: {parameter_value}
```

Imported tests may define additional assertions.

```yaml
imports:
  tests:
    {import_name}: {import_path}

"first item to test":
  {import_name}:
    {parameter_name}: {parameter_value}
    
  assertions:
    - ...
```

Page models can be imported and their properties referenced within the test suite.

```yaml
imports:
  pages:
    {import_name}: {import_path}

"open page":
  actions:
    - open {import_name}
    
  assertions:
    - {import_name}.elements.{element_name} {comparison} {value}
```

## Examples

### Tests Defined Within The Test Suite

```yaml
"open https://www.google.com":
  actions:
    - open "https://www.google.com"

  assertions:
    - "title" is "Google"

"query 'example'":
  actions:
    - set ".gLFyf.gsfi" to "example"
    - click ".FPdoLc.VlcLAe input[name=btnK]"

  assertions:
    - "title" is "example - Google Search"
```

### Parameterised Tests Imported Into The Test Suite

```yaml
# test/open-url-parameterised.yml

actions:
  - open {{ url }}

assertions:
  - url is {{ url }}
  - {{ title_selector}} is {{ expected_title }}
```

```yaml
imports:
  tests:
    # Import name cannot be 'actions' or 'assertions'
    open_url: ../test/open-url-parameterised.yml

"open https://www.google.com":
  open_url:
    url: "https://www.google.com"
    title_selector: "title"
    expected_title: "Google"
```

### Tests Imported Into The Test Suite With Additional Assertions

```yaml
# test/google-search-open-url.yml

actions:
  - open "https://www.google.com"

assertions:
  - "title" is "Google"
```

```yaml
# test/google-search-query-example.yml

actions:
  - set ".gLFyf.gsfi" to "example"
  - click ".FPdoLc.VlcLAe input[name=btnK]"

assertions:
  - "title" is "example - Google Search"
```

```yaml
imports:
  tests:
    google_search_open_url: test/google-search-open-url.yml
    google_search_query_example: test/google-search-query-example.yml

"open https://www.google.com":
  - google_search_open_url
  
  assertions:
    - url is "https://google.com"

"query 'example'":
  - google_search_query_example
```

### Page Model Imported Into The Test Suite

```yaml
# page/google.com.yml

url: https://www.google.com
elements:
  title: "title"
  search_input: ".gLFyf.gsfi"
  search_button: ".FPdoLc.VlcLAe input[name=btnK]"
```

```yaml
imports:
  pages:
    google_com: page/google.com.yml

"open https://www.google.com":
  actions:
    - open google_com

  assertions:
    - google_com.elements.title is "Google"

"query 'example'":
  actions:
    - set google_com.elements.search_input to "example"
    - click google_com.elements.search_button

  assertions:
    - google_com.elements.title is "example - Google Search"
```
