# actions-flutter-validate

Performs checks against Dart and Flutter code to ensure the package does not have any analysis issues, failed tests, or improperly formatted code (as defined by `dart format`).

## Inputs

Name              | Default  | Description
------------------|----------|-------------
`channel`         | `stable` | Channel to pull for Dart / Flutter's SDK
`credentials`     | n/a      | Credentials JSON from pub


## Example usage

```yaml
name: Publish

on:
  pull_request:
    branches: [main]

jobs:
  validate:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout
        uses: actions/checkout@v2
      - name: Setup Flutter
        uses: subosito/flutter-action@v1
        with:
          channel: ${{ inputs.channel }}

      - name: Publish
        uses: peiffer-innovations/actions-pub-publish@v1.0.2
        with:
          credentials: ${{ secrets.CREDENTIALS_JSON }}
```

