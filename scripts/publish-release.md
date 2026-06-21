# Publish Podvault release assets to GitHub

Requires GitHub CLI: https://cli.github.com/

```powershell
# One-time setup
gh auth login

# From repo root
npm run build
gh release create 0.1.0 main.js manifest.json styles.css `
  --repo mcdullzxr/obsidian-podvault `
  --title "Podvault v0.1.0" `
  --notes-file release-notes.md
```

Important: the release **tag must be `0.1.0`** (matching `manifest.json` version), not `v0.1.0`.

If the tag already exists without assets, delete the empty release on GitHub first, or run:

```powershell
gh release upload 0.1.0 main.js manifest.json styles.css --repo mcdullzxr/obsidian-podvault
```
