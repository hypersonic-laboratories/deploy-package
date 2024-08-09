# Deploy Helix Package

Tired of zipping your packages, uploading them on the HELIX Hub, and not knowing if you're doing it correctly?. This action will automatically zip relevant parts of your package and upload it as a new version to HELIX.

## Warning

Make sure you've created the package on the HELIX Hub first: [https://hub.helixgame.com/creations/packages](https://hub.helixgame.com/creations/packages). This action will fail if you attempt to upload a package that hasn't been created yet.

## Using this Action

In your development repository, create a workflow file in `.github/workflows` that utilizes this Github Action and provides `package_name` and `access_token` as inputs. For example, in `.github/workflows/upload.yml`:

```yaml
name: Deploy new version to HELIX

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
