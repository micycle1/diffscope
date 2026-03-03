# DiffScope

Browse a GitHub release diff one file at a time.

Paste any GitHub compare URL and DiffScope fetches the diff, lists every changed file in a sidebar, and only shows the ones you select. Useful when a release spans dozens of files and you only care about a few.

## Usage

Paste a GitHub compare URL:

```
https://github.com/owner/repo/compare/v1.0...v2.0.diff
```

Then check or uncheck files in the sidebar. Use the pattern box to select files by glob (`src/**/*.cpp`) or regex (`/\.h$/`).

## Deploy

Single static HTML file — no build step.

1. Put `index.html` in a repo
2. Enable GitHub Pages (Settings → Pages → Deploy from branch)
3. Done

## Notes

- GitHub doesn't allow browser fetches of `.diff` URLs directly, so requests are proxied through [corsproxy.io](https://corsproxy.io). Only the raw diff text passes through — no credentials.
- For private repos, download the diff locally (`curl ... > patch.diff`) and paste the contents — or self-host a CORS proxy.
