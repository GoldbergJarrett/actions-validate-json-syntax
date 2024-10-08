# GitHub Actions: validate-json-syntax

GitHub Action for validating json syntax.

[JSON Documentation.](https://www.json.org/json-en.html)

This is a simple tool that utilizes a powerful tool, JQ, to do simple syntax validation on JSON.

## Usage

This action can be used as follows:
```yaml
      - uses: GoldbergJarett/actions-validate-json-syntax@v1
```

#### Setup

This action expects that the repo has been checked out.  

```yaml
...
    steps:
      - name: Checkout
        uses: actions/checkout@v4
...
```

### Inputs

There is an option input of a path. Providing a path will ensure that _all_ json in the directory will be validated.

## Examples

```yaml
name: Release Tagger

on: 
  pull_request:
    branches:
      - 'main'

jobs:
  validate-json:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v2

      - name: Validate JSON Syntax
        uses: GoldbergJarett/actions-validate-json-syntax@v1
```
