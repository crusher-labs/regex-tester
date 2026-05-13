# Regex Tester

Test regular expressions against sample text in real time.

Live: <https://crusher-labs.github.io/regex-tester/>

## What it does

Test regular expressions against sample text in real time.

## Privacy

This tool runs entirely in your browser. There is no server. No data is uploaded, no telemetry, no analytics. The only network requests fired are the page-load fetches for the framework's CSS / JS (from `cdn.jsdelivr.net` and `fonts.googleapis.com` / `fonts.gstatic.com`); your inputs and outputs never leave the tab.

## ReDoS protection

The regex match runs in a Web Worker with a 500 ms wall-clock timeout. If a pathological pattern (e.g. nested quantifiers like `(a*)*b` against a long string) doesn't return in time, the main thread terminates the worker, respawns a fresh one, and shows "Pattern timed out — likely catastrophic backtracking." The tab stays responsive throughout.

## Framework / hosting

- Static HTML / CSS / JS deployed via GitHub Pages from this repo's `main` branch.
- UI chrome is the published `crusher-ui-kit@0.1.6` static contract — see the workspace `CLAUDE.md` for the contract details.

## Development

- Open `index.html` directly in a browser. No build, no dependencies.
- Or serve the parent workspace via the hub's preview server: `cd ../../tools-hub && npm run preview` then visit `http://127.0.0.1:8723/utility-tools/regex-tester/`.

## License

MIT.
