# Download an Artifact from EAS

This action can be used to download a specific build artifact from EAS.


## Steps

 - Checkout repository code (via `actions/checkout@v3`)
 - Setup Expo and EAS
 - Download EAS build (via `eas build:list`)

## Usage

See [action.yml](action.yml)

**Example:**

```yaml
steps:
- uses: Mersive-Technologies/gh-actions/eas-download@v1
  with:
    expo-token: ${{ secrets.EXPO_TOKEN }}
    channel: preview
    platform: ios
    commit: ${{ github.sha }}
    output: app.ipa
```

