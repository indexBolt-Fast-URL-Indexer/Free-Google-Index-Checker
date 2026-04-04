# IndexCheck

IndexCheck is an Electron desktop app for checking whether URLs appear in Google search results and then submitting unindexed pages to IndexBolt.

## Current scope

- Built-in browser mode using Electron's Chromium to query `site:` searches
- SERP API mode for `ScraperAPI`, `SerpAPI`, and `Serper`
- Google Search Console mode using user-supplied Google Desktop OAuth credentials
- URL input via paste, file import, drag and drop, or sitemap import
- Real-time progress, result filtering, CSV/JSON export, and clipboard copy
- IndexBolt API key validation, balance display, and submission flow
- Cross-platform packaging via `electron-builder`

## Google Search Console setup

IndexCheck does not ship with shared Google credentials. Each user imports their own Google Cloud Desktop OAuth client JSON, signs in with Google, and selects a Search Console property inside the app. This avoids central OAuth verification burden for the desktop app, but it means users need to complete their own Google Cloud setup first.

The full setup walkthrough is in [docs/google-search-console-setup.md](./docs/google-search-console-setup.md).

## Known gap

- Google OAuth apps left in Testing mode may require users to reconnect periodically because refresh token lifetime can be limited during testing.

## Development

```bash
cd apps/indexcheck
npm install
npm run dev
```

## Build

```bash
cd apps/indexcheck
npm run build
npm run dist
```
