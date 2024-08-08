# Deploy Helix Package

Tired of zipping your packages, drag'n'drop them into Hub and not knowing exactly if you are doing it right?. This action will automatically zip your package and upload it to the Helix Platform.

## Using this your repository

In your other repository, create a workflow file that uses the custom action and provides the `package_name` and `access_token` as an input. For example, in `.github/workflows/upload.yml`:

```yaml
name: Upload Package to Helix

on:
  push:
    branches:
      - main

jobs:
  upload-package:
    runs-on: ubuntu-latest

    steps:
      - name: Use deploy package action
        uses: hypersonic-laboratories/deploy-package@main
        with:
          access_token: ${{ secrets.ACCESS_TOKEN }}
          package_name: 'my-awesome-package'

```

## Setting Up Secrets

Ensure that the ACCESS_TOKEN secret is set in the repository where you use this action. Navigate to Settings > Secrets > Actions and add a new secret named ACCESS_TOKEN. You can generate an Access Token on the [HELIX Hub](https://hub.helixgame.com/account/tokens).
