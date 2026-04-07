# TestDino - AWS CodeBuild Playwright Example

This is an example project that shows how to run Playwright tests on AWS CodeBuild with 4 shard passes and upload the merged report to TestDino.

Tool URL: [AWS CodeBuild](https://aws.amazon.com/codebuild/)

The example build:

- installs dependencies and Playwright browsers
- runs Playwright tests in 4 shard passes
- stores blob reports from each shard pass
- merges the shard reports into `playwright-report/report.json`
- uploads the merged report to TestDino

Set the `TESTDINO_TOKEN` environment variable in CodeBuild.

Get your token from [testdino](https://app.testdino.com).

Copy this folder into the root of your repository and keep `buildspec.yml` at the repository root unless you configure a custom buildspec path.

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

