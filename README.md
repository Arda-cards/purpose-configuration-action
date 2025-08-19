# gradle build

[![ci](https://github.com/Arda-cards/purpose-configuration-action/actions/workflows/ci.yaml/badge.svg?branch=main)](https://github.com/Arda-cards/purpose-configuration-action/actions/workflows/ci.yaml?query=branch%3Amain)
[CHANGELOG.md](CHANGELOG.md)

This action reads the file referenced by the `locator_url` and returns its content as a set of GitHub output.
This set defines the minimal configuration required to deploy a component to a partition, see the [action.yaml](action.yaml).

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
