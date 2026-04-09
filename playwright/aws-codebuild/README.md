# TestDino Playwright Example for AWS CodeBuild

This example runs Playwright tests in 4 [AWS CodeBuild](https://aws.amazon.com/codebuild/) shard passes, merges the results into `playwright-report/report.json`, and uploads the merged report to [TestDino](https://app.testdino.com).

## Prerequisites

- [Node.js](https://nodejs.org/) v16+
- [npm](https://www.npmjs.com/)
- TestDino API key for report upload
- AWS account with CodeBuild access

---

## Get Your TestDino API Key

1. Sign in to [testdino](https://app.testdino.com).
2. Create an organization and project.
3. Generate an API key from the project setup or settings page.
4. Copy the key and keep it secret.

## Add The CodeBuild Environment Variable

1. Open your AWS CodeBuild project.
2. Choose `Edit`.
3. Open the `Environment` section.
4. Add an environment variable named `TESTDINO_TOKEN`.
5. Paste your TestDino API key as the value.
6. Save the project.

## Use This Example

1. Copy this folder into your repository root.
2. Keep `buildspec.yml` at the repository root unless you use a custom buildspec path.
3. Run:

```bash
npm ci
npx playwright install
```

4. Start the CodeBuild build.

## Local Run

```bash
npm ci
npx playwright install
npx playwright test
npx tdpw upload ./playwright-report --token="YOUR_TESTDINO_TOKEN"
```

## What Happens In CI

- AWS CodeBuild runs 4 Playwright shard passes
- blob reports are collected from each shard pass
- the reports are merged into `playwright-report/report.json`
- the merged report is uploaded to TestDino

## Support

Documentation: [docs.testdino.com](https://docs.testdino.com)

Email: [support@testdino.com](mailto:support@testdino.com)

## License

[MIT](../../LICENSE)
