# Setup Mersive Expo Project (with Yarn)

This GitHub Action is intended to be used by worflows within Expo projects that use Yarn as the package manager.
The action also configures NPM credentials for accessing Mersive's private NPM repository, allowing your application to have internal dependencies.

## Steps

 - Checkout repository code (via `actions/checkout@v3`)
 - Setup Node with caching optimization (via `actions/setup-node@v3`)
 - Authenticate with Mersive's NPM repository
 - Install dependencies (i.e., `yarn install`)

## Usage

See [action.yml](action.yml)

**Example:**

```yaml
steps:
- uses: Mersive-Technologies/gh-actions/expo-setup@v1
  with:
    npm-user: ${{ secrets.NPM_USER }}
    npm-pass: ${{ secrets.NPM_PASS }}
    npm-email: ${{ secrets.NPM_EMAIL }}
```

