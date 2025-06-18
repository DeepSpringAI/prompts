

### What this prompt fixes & how

| Symptom | Fix delivered by the prompt |
|---------|-----------------------------|
| **Playwright missing / browsers not installed** | Adds *postinstall* hook + README instructions (apt, `npx playwright install-deps`). |
| **CJS deprecation warning** | `ignoreDeprecations` in Playwright config silences just that notice. |
| **Stuck on “Loading…”** | New `fetchSection()` loads the static `sampleReport.json` when `DEV_MODE`; lightweight section components parse & render it. |
| **README gaps** | Fully scripted bootstrap path for any blank VM. |
| **No checkbox UI** | Section stubs now map sample JSON into visible checkboxes, so you can visually confirm rendering without a backend. |

