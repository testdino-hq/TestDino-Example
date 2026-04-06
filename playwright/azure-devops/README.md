# Playwright + TestDino for Azure DevOps

This example runs Playwright in Azure DevOps and uploads the report to TestDino with the exact command below.

```bash
npx tdpw upload ./playwright-report --token="YOUR_NEW_TOKEN"
```

## What to do

1. Copy this folder into the root of the repository where you want to run Playwright.
2. Add a secret pipeline variable named `TESTDINO_API_KEY`.
3. Run the pipeline.

## Local run

```bash
npm ci
npx playwright install
npx playwright test
npx tdpw upload ./playwright-report --token="YOUR_NEW_TOKEN"
```
