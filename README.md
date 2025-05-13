# GitHub Action For Magento Compilation

This action is used to compile Magento and validate composer.json file.

**Author:** Patryk Waluś (patryk.walus@vaimo.com)

## Supported versions

- v1
    - Magento compilation

## Compatibility

This action is compatible only with the custom Docker image: [vaimo/image-action-magento](https://github.com/vaimo/image-action-magento).

# Usage

```yaml
jobs:
  code-sniffer:
    runs-on: ubuntu-latest
    container:
      image: ghcr.io/vaimo/image-action-magento:${{inputs.version}}-v1
    steps:
      - name: Compilation action
        uses: vaimo/action-magento-compilation@v1
        with:
          # Secret variable that stores the contents of auth.json.
          # Required
          composer-auth: ${{secrets.COMPOSER_AUTH}}
          # Directory name that will be used to run action.
          # Optional - if not specified then uses the root directory.
          working-directory: ${{env.working-directory}}
```