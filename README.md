# Push to Paragon GitHub Action

This GitHub Action allows you to push to Paragon using the Paragraph CLI.

## Usage

```yaml
name: Push to Paragon

on:
  push:

  # Allows you to run this workflow manually from the Actions tab
  workflow_dispatch: 

jobs:
  push_to_paragon:
    name: Push to Paragon
    runs-on: ubuntu-latest
      
    steps:
      - uses: actions/checkout@v4
      - id: push
        uses: useparagon/paragraph-push-action@v1
        with:
          paragonKey: ${{ secrets.PARAGON_CLI_KEY }}
          paragonZeusUrl: ${{ secrets.ZEUS_URL }}
          paragonDashboardUrl: ${{ secrets.DASHBOARD_URL }}
```

Make sure to replace ${{ secrets.PARAGON_CLI_KEY }}, ${{ secrets.ZEUS_URL }}, and ${{ secrets.DASHBOARD_URL }} with your actual secrets. Also, ensure to use the correct version of the action.

## Inputs
- `paragonKey` (Required)\
Paragon CLI key for authentication.

- `paragonZeusUrl` (Optional)\
URL for Paragon Zeus.

- `paragonDashboardUrl` (Optional)\
URL for Paragon Dashboard.
