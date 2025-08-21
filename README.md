# Purpose Configuration Action

[![ci](https://github.com/Arda-cards/purpose-configuration-action/actions/workflows/ci.yaml/badge.svg?branch=main)](https://github.com/Arda-cards/purpose-configuration-action/actions/workflows/ci.yaml?query=branch%3Amain)
[CHANGELOG.md](CHANGELOG.md)

This action reads the file referenced by the `locator_url` and returns its content as a set of GitHub output.
This set defines the minimal configuration required to deploy a component to a partition.

The resource designated by the `locator_url` is in the properties format, keys and values separated by an equal sign.

| Key             | Required               | Description                                                                         |
|-----------------|------------------------|-------------------------------------------------------------------------------------|
| aws_role        | yes                    | The arn of a rol that GitHub can assume.                                            |
| aws_region      | yes                    | The AWS region to connect to for authentication.                                    |
| cluster_name    | yes                    | The name of a Kubernetes cluster to deploy components to.                           |
| deployment_gate | no, defaults to `none` | `none` to automatically proceed with the deployment, `manual` to wait for approval. |

## Arguments

See [action.yaml](action.yaml).

## Usage

```yaml
- id: purpose_config
uses: Arda-cards/purpose-configuration-action@v2
with:
locator_url: "${{ vars.PURPOSE_LOCATOR_BASE_URL }}/dev.properties?ref=v1"
locator_url_token: "${{ secrets.PURPOSE_LOCATOR_READER_TOKEN }}"
```

## Permission Required

```yaml
permissions:
{}
```
