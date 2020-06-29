# WoW Lua Lint

This action will lint all lua files specified for a given repository and check for any syntax issues (under the hood it uses `luac -p path/to/files`)

## Usage

The following shows an example of how to use this action in a workflow.

.github/workflows/lint.yml

```yaml
name: Lint
on: [push]

jobs:
  lint:
    name: Lint
    runs-on: ubuntu-latest
    steps:
      - name: checkout
        uses: actions/checkout@v2
        with:
          repository: 'ps-wow/action-test-repo'
      - name: wow-lint
        uses: davidcraig/action-wow-lint@1.0.0
        with:
            path-to-files: 'src/test.lua'
```