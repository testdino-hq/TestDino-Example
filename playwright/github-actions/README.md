# Playwright + TestDino for GitHub Actions

This example runs Playwright in GitHub Actions and uploads the report to TestDino with the exact command below.

```bash
npx tdpw upload ./playwright-report --upload-html --token="YOUR_NEW_TOKEN"
```

## What to do

1. Copy this folder into the root of the repository where you want to run Playwright.
2. Add a GitHub Actions secret named `TESTDINO_API_KEY`.
3. Push a commit or run the workflow manually.

## Local run

```bash
npm ci
npx playwright install
npx playwright test
npx tdpw upload ./playwright-report --upload-html --token="YOUR_NEW_TOKEN"
```
