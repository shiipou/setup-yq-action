# setup-yq-action
GitHub Action to setup `yq` command for yaml and json parsing


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
        id: setup-yq
        uses: shiipou/setup-yq-action@v2.2.0
      - name: get version
        run: |
          VERSION=$(yq '.dependency.my_component.git.ref' pubspec.yaml)
```
