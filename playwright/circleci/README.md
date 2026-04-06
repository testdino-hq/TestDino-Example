# Playwright + TestDino for CircleCI

This example runs Playwright in CircleCI and uploads the report to TestDino with the exact command below.

```bash
npx tdpw upload ./playwright-report --token="YOUR_NEW_TOKEN"
```

## What to do

1. Copy this folder into the root of the repository where you want to run Playwright.
2. Add an environment variable named `TESTDINO_API_KEY` in a CircleCI project variable or context.
3. Trigger the workflow.

## Local run

```bash
npm ci
npx playwright install
npx playwright test
npx tdpw upload ./playwright-report --token="YOUR_NEW_TOKEN"
```
