# Deploy Helix Package

Tired of zipping your packages, drag'n'drop them into Hub and not knowing exactly if you are doing it right?. This action will automatically zip your package and upload it to the Helix Platform.

## Using this your repository

In your other repository, create a workflow file that uses the custom action and provides the `package_name` and `access_token` as an input. For example, in `.github/workflows/upload.yml`:

```yaml
name: Upload Package

on:
  push:
    branches:
      - main

jobs:
  upload-package:
    runs-on: ubuntu-latest

    steps:
      - name: Use custom deploy package action
        uses: <your-username>/deploy-package-action@main
        with:
          access_token: ${{ secrets.ACCESS_TOKEN }}
          package_name: 'my-awesome-package'

```

## Setting Up Secrets

Ensure that the ACCESS_TOKEN secret is set in the repository where you use this action. Navigate to Settings > Secrets > Actions and add a new secret named ACCESS_TOKEN.
