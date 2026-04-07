# TestDino - Azure DevOps Playwright Example

This is an example project that shows how to run Playwright tests on Azure DevOps with 4 shards and upload the merged report to TestDino.

Tool URL: [Azure DevOps](https://azure.microsoft.com/products/devops)

The example pipeline:

- installs dependencies and Playwright browsers
- runs Playwright tests in 4 matrix shards
- stores blob reports from each shard
- merges the shard reports into `playwright-report/report.json`
- uploads the merged report to TestDino
- still attempts merge and upload even if one or more test shards fail

Set the `TESTDINO_TOKEN` secret pipeline variable.

Azure DevOps secret pipeline variables are not automatically exposed to scripts, so the upload step maps `TESTDINO_TOKEN` through `env:`.

Get your token from [testdino](https://app.testdino.com).

Copy this folder into the root of your repository and keep `azure-pipelines.yml` at the repository root.

Local commands:

```bash
npm ci
npx playwright install
npx playwright test
npx tdpw upload ./playwright-report --token="YOUR_TESTDINO_TOKEN"
```

## Sample tests included

This example includes multiple test files so shard-based CI examples actually distribute work.

The sample suite includes:

- passing tests across multiple spec files
- one skipped test for reporting coverage
- one expected-failure test using `test.fail()` for reporting coverage

The skipped and expected-failure tests are intentional example cases. They are included to show richer reporting behavior without making the pipeline genuinely flaky.

