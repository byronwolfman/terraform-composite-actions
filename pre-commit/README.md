<p align="center">
  <img src="../.github/images/pre-commit.svg " alt="Pre-Commit" height="296px">
</p>
<h1 style="font-size: 56px; margin: 0; padding: 0;" align="center">
  pre-commit
</h1>

## Usage

The `clowdhaus/terraform-composite-actions/pre-commit` action will install the following tools which are intended to support the pre-commit hooks used within Terraform modules:

- [terraform](https://github.com/hashicorp/terraform) using provided `terraform-version` input
- [pre-commit](https://github.com/pre-commit/pre-commit)
- [tflint](https://github.com/terraform-linters/tflint)
- [terraform-docs](https://github.com/terraform-docs/terraform-docs) using provided `terraform-docs-version` input

```yml
jobs:
  pre-commit:
    name: Pre-commit hooks execute
    runs-on: ubuntu-latest
    steps:
      - name: Sign AWS Lambda artifact
        uses: clowdhaus/terraform-composite-actions/pre-commit@main
        with:
          terraform-version: 1.0.2
          terraform-docs-version: v15.0.0
          args: "--all-files --color always --show-diff-on-failure"
```
