# TestDino Examples

Ready-to-use Playwright examples for CI/CD providers supported by TestDino.

Each example shows how to:

- run Playwright tests in shards
- merge the results into `playwright-report/report.json`
- upload the merged report to TestDino

## Prerequisites

- Node.js and npm
- A TestDino account
- A `TESTDINO_TOKEN`
- Access to the CI/CD provider used by the example

Get your token from [testdino](https://app.testdino.com).

## Examples

- [`playwright/github-actions`](./playwright/github-actions/README.md)
- [`playwright/gitlab-ci`](./playwright/gitlab-ci/README.md)
- [`playwright/circleci`](./playwright/circleci/README.md)
- [`playwright/jenkins`](./playwright/jenkins/README.md)
- [`playwright/azure-devops`](./playwright/azure-devops/README.md)
- [`playwright/aws-codebuild`](./playwright/aws-codebuild/README.md)

## How To Use

1. Pick the example for your CI/CD provider.
2. Copy that folder into your repository root.
3. Add `TESTDINO_TOKEN` in your CI/CD platform.
4. Follow the README inside that example folder.

## Support

Documentation: [docs.testdino.com](https://docs.testdino.com)

Email: [support@testdino.com](mailto:support@testdino.com)

## License

[MIT](./LICENSE)
