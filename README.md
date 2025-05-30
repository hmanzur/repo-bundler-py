# 🧱 repo-bundler-py

GitHub Actions workflow for generating and publishing versioned artifacts from Python applications during the CI flow.

## 🚀 Purpose

This repository defines a manual GitHub Actions workflow (`workflow_dispatch`) that:

- Clones a target Python application repository
- Automatically computes a version string from Git metadata
- Bundles the codebase into a distributable archive
- Publishes the archive as a GitHub Actions artifact

It's designed to support CI pipelines that need consistent versioned artifacts, especially during early integration setups.

## 🎓 Used In

This workflow is part of the [SoftServe PeEx program](https://softserveinc.github.io/) and is being used to build and version artifacts from:

👉 [edonosotti/ci-cd-tutorial-sample-app](https://github.com/edonosotti/ci-cd-tutorial-sample-app)

## 🚀 How to Use

This workflow runs manually via the GitHub UI under the **Actions** tab.

### Inputs

| Name          | Description                                  | Required | Default             |
|---------------|----------------------------------------------|----------|---------------------|
| `repo`        | Repository to clone (in `owner/repo` format) | ✅       | N/A                 |
| `ref`         | Git reference (branch, tag, or SHA)          | ✅       | N/A                 |
| `subdir`      | Optional subdirectory to archive             | ❌       | `.` (entire repo)   |

To trigger the workflow:

1. Go to the **Actions** tab.
2. Select `📦 Build and Bundle Python App`.
3. Click **Run workflow**.
4. Fill in the required inputs.

## 📦 Output

The workflow generates an archive (e.g., `sample-app-v1.2.3.tar.gz`) and uploads it to the run's **Artifacts** section. Versions are generated using Git metadata, e.g.: `v1.2.3+5.gabc1234

## 📝 License

MIT License
