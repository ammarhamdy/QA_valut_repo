
https://playwright.dev/docs/intro
---

# Install playwright Extensions for VS code  
[Playwright Test for VSCode](https://marketplace.visualstudio.com/items?itemName=ms-playwright.playwright)

# Install every thing that `playwight` need
```sh
npm init playwright@latest --yes "--" . '--quiet' '--browser=chromium' '--browser=firefox' '--browser=webkit' '--install-deps'
```
Or press: `Ctr` + `Shift` + `p` and type `install playwright`

---

# Project Files

Check out the following files:
- `./tests/example.spec.ts` — Example end-to-end test
- `./playwright.config.ts` — Playwright Test configuration

# Playwright Commands
Inside that directory (project directory), you can run several commands:
```bash
npx playwright test
```

Runs the end-to-end tests.
```sh
npx playwright test --ui
```

Starts the interactive UI mode.
```sh
npx playwright test --project=chromium
```

Runs the tests only on Desktop Chrome.
```sh
npx playwright test example
```

Runs the tests in a specific file.
```sh
npx playwright test --debug
```

Runs the tests in debug mode.
```sh
npx playwright codegen
```

