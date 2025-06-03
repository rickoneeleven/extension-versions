# Chrome Extension Version Registry

This repository serves as a centralized version registry for unpacked Chrome extensions.

## How It Works

1. **Extension Version Checking**: Each extension includes `version-checker.js` which periodically checks this registry
2. **Version Registry**: `versions.json` contains the latest version number for each extension
3. **Automatic Updates**: When extensions detect they're outdated, they show notifications

## versions.json Format

```json
{
  "extension-name": "1.2.3",
  "another-extension": "2.0.1"
}
```

## Adding New Extensions

To add a new extension to the registry:
1. Add an entry to `versions.json`
2. Include `version-checker.js` in your extension
3. Call `new VersionChecker('extension-name').checkVersion()` in your background script

## Updating Versions

When you release a new version:
1. Update the version in your extension's `manifest.json`
2. Update the version in this registry's `versions.json`
3. Extensions will automatically detect the update within 24 hours

## Current Extensions

- **ai-prompt-manager**: AI Prompt Manager extension for storing and managing AI prompts
