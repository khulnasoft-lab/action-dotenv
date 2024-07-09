## Why

GitHub Actions already contains plenty of [context](https://docs.github.com/en/actions/reference/context-and-expression-syntax-for-github-actions) for use within Actions workflows.

However, it's very limited, and does not include the entirety of the repository metadata.

## Inputs

| input  | required | default | description         |
| ------ | -------- | ------- | ------------------- |
| `file` | ❌      | `.env`   | path to `.env` file |

## Usage

``` yaml
jobs:
  job:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v2

      - id: metadata
        uses: khulnasoft-lab/action-dotenv@v1

      - run: echo ${{ env.foo }} ${{ env.bar }}
