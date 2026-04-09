# TestDino Playwright Example for Azure DevOps

This example runs Playwright tests in 4 [Azure DevOps](https://azure.microsoft.com/products/devops) shards, merges the results into `playwright-report/report.json`, and uploads the merged report to [TestDino](https://app.testdino.com).


## Prerequisites

- [Node.js](https://nodejs.org/) v16+
- [npm](https://www.npmjs.com/)
- TestDino API key for report upload
- Azure DevOps project with pipelines enabled

---

## Get Your TestDino API Key

1. Sign in to [testdino](https://app.testdino.com).
2. Create an organization and project.
3. Generate an API key from the project setup or settings page.
4. Copy the key and keep it secret.

## Add The Azure DevOps Secret Variable

1. Open your Azure DevOps pipeline.
2. Edit the pipeline.
3. Open `Variables`.
4. Create a variable named `TESTDINO_TOKEN`.
5. Paste your TestDino API key.
6. Mark the variable as secret.
7. Save the pipeline.

## Use This Example

1. Copy this folder into your repository root.
2. Keep `azure-pipelines.yml` at the repository root.
3. Run:

```bash
npm ci
npx playwright install
```

4. Run the pipeline in Azure DevOps.

## Local Run

```bash
npm ci
npx playwright install
npx playwright test
npx tdpw upload ./playwright-report --token="YOUR_TESTDINO_TOKEN"
```

## What Happens In CI

- Azure DevOps runs 4 Playwright shards
- blob reports are collected from each shard
- the reports are merged into `playwright-report/report.json`
- the merged report is uploaded to TestDino

<img src="../../assets/azure-devops/testdino-azuredevops-pipeline.png" alt="Azure DevOps pipeline run" width="600" />

<img src="../../assets/azure-devops/testdino-azuredevops-testrun.png" alt="TestDino test run from Azure DevOps" width="600" />

<img src="../../assets/azure-devops/testdino-azuredevops-upload.png" alt="Azure DevOps upload step" width="600" />



## Support

Documentation: [docs.testdino.com](https://docs.testdino.com)

Email: [support@testdino.com](mailto:support@testdino.com)

## License

[MIT](../../LICENSE)
