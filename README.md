## Add an extension
1. Give the extension its own repo. `manifest.json` must be in the repo root.
2. Add one entry to `extensions.json` and commit:
   `{ "repo": "my-extension", "category": "Productivity" }`
3. The store reads name, version, description, icon and stars from GitHub by itself.

Optional fields per entry: `name`, `tagline`, `features` (list), `icon` (image URL), `version`, `chrome` (Chrome Web Store link; the button becomes "Add to Chrome").
Use `"repo": "other-user/name"` for a repo under a different account.

## Download button
The store links the newest **GitHub Release** `.zip`. If there is no release, it links the repo's `main` branch zip.
The extension package includes `.github/workflows/release.yml`: push a tag like `v1.0.1` and GitHub builds the release zip for you.

## Notes
- GitHub allows 60 API requests per hour per visitor. The store caches results for 1 hour, so this is enough for normal use.
- Users install with: unzip, `chrome://extensions`, Developer mode, Load unpacked.
