# Create EAS build for Expo (with Yarn) project

This GitHub Action is intended to be used by worflows within Expo projects that use Yarn as the package manager.
The action also configures NPM credentials for accessing Mersive's private NPM repository, allowing your application to have internal dependencies.
Once the project is setup, an EAS build will be created.

By default, a build is only created when we have a Yarn cache miss, unless you set `force: true`.


## Steps

 - Checkout repository code (via `actions/checkout@v3`)
 - Setup Node with caching optimization (via `actions/setup-node@v3`)
 - Authenticate with Mersive's NPM repository
 - Install dependencies (i.e., `yarn install`)
 - Trigger EAS build (i.e., `eas-build`)

## Usage

See [action.yml](action.yml)

**Example:**

```yaml
steps:
- uses: Mersive-Technologies/gh-actions/eas-build@v1
  with:
    platform: ios
    profile: preview
    expo-token: ${{ secrets.EXPO_TOKEN }}
    npm-user: ${{ secrets.NPM_USER }}
    npm-pass: ${{ secrets.NPM_PASS }}
    npm-email: ${{ secrets.NPM_EMAIL }}
```

