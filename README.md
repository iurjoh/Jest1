# Jest1

A small JavaScript learning repository for unit tests and DOM tests with Jest.

[Português (Brasil)](README.pt-BR.md)

## Status and process record

Source reviewed on 2026-10-01. The original README contained only the repository name. No dated planning notes, wireframes or original development diary were found in the reviewed files. This update describes the existing code and test structure, not a completed calculator or production application. Tests and the browser demo were not run in this update.

## Idea, architecture and design

- `script/calc.js`: an exported addition function.
- `script/button.js`: changes paragraph `#par` to "You Clicked" and exports the function for CommonJS tests.
- `index.html`: one heading, a "Click Me" button and an empty paragraph.
- `script/tests/calc.test.js`: one addition assertion; subtraction, multiplication and division groups are empty placeholders.
- `script/tests/button.test.js`: jsdom tests reading index.html, calling the exported function and checking paragraph content and heading count.

The design is a minimal HTML test fixture, not a styled product. There is no API or database in this structure. package.json declares Jest `^26.6.3` as a development dependency and `npm test` runs Jest.

## Setup and test

Use a disposable local environment with a compatible Node.js/npm version. These are historical dependencies; review them before reuse.

```bash
npm ci
npm test
```

There are three implemented test cases: addition, paragraph update and heading existence. Tests were not rerun here; no current pass or coverage percentage is claimed. The DOM tests call the function directly, so they do not prove that the real browser's script loading or click handler works.

## Known issues and next checks

`index.html` refers to `scripts/button.js`, but the actual directory is `script/`. The file also uses `module.exports`, which needs a CommonJS context or suitable browser handling. The static demo therefore needs review before being presented as working. No code was changed to hide these issues.

Before reuse, verify the script path and browser/module boundary, test an actual click, decide numeric input behavior and implement/test other calculator operations if wanted. The committed `node_modules/` folder should not substitute for a clean install from the manifest and lockfile.

## Snapshots

No application screenshot was verified or added. After fixing and checking the demo, capture its initial and clicked states using dated files under `docs/assets/`, with no personal data. Test-output captures should show the actual command and result. Add links only after the files exist.

## Credits and licensing

The existing package manifest declares ISC; that declaration was preserved and no new license file was added. Jest and its dependencies retain their own licenses. This README does not claim original authorship of any third-party exercise material whose provenance is not established in the reviewed files.
