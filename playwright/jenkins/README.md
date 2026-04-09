# TestDino Playwright Example for Jenkins

This example runs Playwright tests in 4 [Jenkins](https://www.jenkins.io/) shards, merges the results into `playwright-report/report.json`, and uploads the merged report to [TestDino](https://app.testdino.com).


## Prerequisites

- [Node.js](https://nodejs.org/) v16+
- [npm](https://www.npmjs.com/)
- TestDino API key for report upload
- Jenkins instance with pipeline support

---

## Get Your TestDino API Key

1. Sign in to [testdino](https://app.testdino.com).
2. Create an organization and project.
3. Generate an API key from the project setup or settings page.
4. Copy the key and keep it secret.

## Add The Jenkins Credential

1. Open Jenkins.
2. Go to `Manage Jenkins` -> `Credentials`.
3. Open the store where you want to add the secret.
4. Click `Add Credentials`.
5. Set `Kind` to `Secret text`.
6. Paste your TestDino API key into `Secret`.
7. Set the `ID` to `TESTDINO_TOKEN`.
8. Save the credential.

## Use This Example

1. Copy this folder into your repository root.
2. Keep `Jenkinsfile` at the repository root.
3. Run:

```bash
npm ci
npx playwright install
```

4. Run the Jenkins pipeline.

## Local Run

```bash
npm ci
npx playwright install
npx playwright test
npx tdpw upload ./playwright-report --token="YOUR_TESTDINO_TOKEN"
```

## What Happens In CI

- Jenkins runs 4 Playwright shards
- blob reports are collected from each shard
- the reports are merged into `playwright-report/report.json`
- the merged report is uploaded to TestDino

<img src="../../assets/jenkins/testdino-jenkins-pipeline.png" alt="Jenkins pipeline run" width="800" />


<img src="../../assets/jenkins/testdino-jenkins-testrun.png" alt="TestDino test run from Jenkins" width="800" />

<img src="../../assets/jenkins/testdino-jenkins-upload.png" alt="Jenkins upload step" width="800" />

## Support

Documentation: [docs.testdino.com](https://docs.testdino.com)

Email: [support@testdino.com](mailto:support@testdino.com)

## License

[MIT](../../LICENSE)
