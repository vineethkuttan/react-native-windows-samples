# React Native for Windows — Documentation Website (v2)

Documentation website for [React Native for Windows](https://github.com/microsoft/react-native-windows), powered by [Docusaurus 3.9](https://docusaurus.io/).

This site covers **React Native Windows versions 0.83 and 0.84**. For documentation on version 0.82 and earlier, visit the [legacy documentation site](https://microsoft.github.io/react-native-windows/v1/).

## Prerequisites

- [Node.js](https://nodejs.org/) **v18 or higher**
- npm (included with Node.js)

## Installation

```bash
cd websitev2
npm install
```

## Local Development

```bash
npm start
```

This starts a local development server (typically at `http://localhost:3000/react-native-windows/`) and opens a browser window. Most changes are reflected live without restarting the server.

## Build

```bash
npm run build
```

Generates static content into the `build/` directory. You can preview the production build locally with:

```bash
npm run serve
```

## Deployment

```bash
GIT_USER=<Your GitHub username> npm run deploy
```

Uses SSH by default. Set `USE_SSH=false` to use HTTPS instead.

## Versioning

This site uses [Docusaurus versioning](https://docusaurus.io/docs/versioning) to maintain documentation for multiple React Native Windows releases.

### Current Versions

| Version | Status | URL Path |
|---------|--------|----------|
| **0.84** | Latest (default) | `/docs/...` |
| **0.83** | Maintained | `/docs/0.83/...` |
| **≤0.82** | Legacy | Served from [old site](https://microsoft.github.io/react-native-windows/v1/) |

### How Versioning Works

- **`docs/`** — The shared source docs directory (at the repo root).
- **`versioned_docs/version-X.XX/`** — Snapshot of docs for each specific version.
- **`versioned_sidebars/version-X.XX-sidebars.json`** — Sidebar configuration for each version.
- **`versions.json`** — Lists all active versions (currently `["0.84", "0.83"]`).

The version dropdown in the navbar includes a link to the legacy Docusaurus v1 site for versions 0.82 and earlier.

### Adding a New Version

When a new React Native Windows version is released:

1. Update the docs in `versioned_docs/` with a new version snapshot:
   ```bash
   npx docusaurus docs:version X.XX
   ```
2. Update `docusaurus.config.js` to include the new version in `onlyIncludeVersions` and set `lastVersion`.
3. Build and test locally before deploying.

## Project Structure

```
websitev2/
├── docusaurus.config.js   # Main site configuration
├── sidebars.js            # Sidebar navigation structure
├── versions.json          # Active documentation versions
├── package.json           # Dependencies and scripts
├── babel.config.js        # Babel configuration
├── src/
│   ├── css/
│   │   └── custom.css     # Custom theme styles
│   └── pages/
│       ├── index.js       # Homepage
│       ├── index.module.css
│       ├── resources.js   # Resources page
│       └── support.md     # Support page
├── static/                # Static assets (images, icons, CSS, JS)
├── versioned_docs/        # Versioned documentation snapshots
│   ├── version-0.83/
│   └── version-0.84/
└── versioned_sidebars/    # Versioned sidebar configurations
    ├── version-0.83-sidebars.json
    └── version-0.84-sidebars.json
```

## Related

- [React Native for Windows](https://github.com/microsoft/react-native-windows)
- [React Native for macOS](https://github.com/microsoft/react-native-macos)
- [Docusaurus Documentation](https://docusaurus.io/docs)
