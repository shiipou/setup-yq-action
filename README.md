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
        id: setup-yq
        uses: shiipou/setup-yq-action@v2.0.1
      - name: get version
        run: |
          ${{ steps.setup_yq.outputs.yq-binary }} '.dependency.my_component.git.ref' pubspec.yaml
```
