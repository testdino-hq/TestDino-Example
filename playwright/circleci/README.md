# TestDino - CircleCI Playwright Example

This is an example project that shows how to run Playwright tests on CircleCI with 4 parallel containers and upload the merged report to TestDino.

Tool URL: [CircleCI](https://circleci.com/)

The example config:

- installs dependencies
- runs Playwright tests in 4 shards
- stores blob reports from each shard
- merges the shard reports into `playwright-report/report.json`
- uploads the merged report to TestDino

Set the `TESTDINO_TOKEN` environment variable in CircleCI. The sample also accepts `TESTDINO_API_KEY` for consistency with cross-provider setup guides.

Get your token from [testdino](https://app.testdino.com).

Copy this folder into the root of your repository and keep `.circleci/config.yml` in the same location.

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

