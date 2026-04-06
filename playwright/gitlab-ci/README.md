# Playwright + TestDino for GitLab CI

This example runs Playwright in GitLab CI and uploads the report to TestDino with the exact command below.

```bash
npx tdpw upload ./playwright-report --token="YOUR_NEW_TOKEN"
```

## What to do

1. Copy this folder into the root of the repository where you want to run Playwright.
2. Add a GitLab CI/CD variable named `TESTDINO_API_KEY`.
3. Run a pipeline from a merge request, the default branch, or the manual pipeline UI.

## Local run

```bash
npm ci
npx playwright install
npx playwright test
npx tdpw upload ./playwright-report --token="YOUR_NEW_TOKEN"
```
