# TestDino Examples

Welcome to the **TestDino Examples** directory. This collection shows how to integrate [TestDino](https://app.testdino.com) with Playwright across different CI/CD providers.

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

## Playwright

Examples demonstrating Playwright integration with TestDino, including sharding, report merging, and CI setup.

### CI

| Example | Description |
| :--- | :--- |
| [**AWS CodeBuild**](./playwright/aws-codebuild/README.md) | Run Playwright tests in AWS CodeBuild |
| [**Azure DevOps**](./playwright/azure-devops/README.md) | Integration with Azure DevOps pipelines |
| [**CircleCI**](./playwright/circleci/README.md) | Run Playwright tests in CircleCI |
| [**GitHub Actions**](./playwright/github-actions/README.md) | Run Playwright tests in GitHub Actions |
| [**GitLab CI**](./playwright/gitlab-ci/README.md) | Run Playwright tests in GitLab CI/CD |
| [**Jenkins**](./playwright/jenkins/README.md) | Run Playwright tests in Jenkins |

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
