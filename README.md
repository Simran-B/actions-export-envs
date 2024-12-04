# actions-export-envs

This action exports `ACTIONS_RUNTIME_TOKEN`, `ACTIONS_RUNTIME_URL`, and `ACTIONS_CACHE_URL`.

## Usage

```yaml
name: CI

on:
  push:
  pull_request:

jobs:
  main:
    runs-on: ubuntu-22.04
    steps:
      - uses: actions/checkout@v3

      - uses: Simran-B/actions-export-envs@v1.2.0
        id: envs

      - run: make build
        env:
          ACTIONS_RUNTIME_TOKEN: ${{ steps.envs.outputs.ACTIONS_RUNTIME_TOKEN }}
          ACTIONS_RUNTIME_TOKEN_URL: ${{ steps.envs.outputs.ACTIONS_RUNTIME_URL }}
          ACTIONS_CACHE_URL: ${{ steps.envs.outputs.ACTIONS_CACHE_URL }}
```
