# setup-yq-action
GitHub Action to setup the `jq` and `yq` command for yaml and json parsing


Example of use :
```yaml
name: Release

on: [ "push" ]

jobs:
  parse_yaml:
    name: Parse Yaml
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v2
      - name: Install yq
        uses: shiipou/setup-yq-action@v1
      - name: get version
        run: |
          yq '.dependency.my_component.git.ref' pubspec.yaml
```
