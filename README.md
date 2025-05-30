# 🧱 Repo Bundler - CI Artifact Versioning

This GitHub Actions workflow automates the process of cloning a repository, running tests, and bundling the project into an artifact with versioning. It is designed to be reused or dispatched for CI/CD flows.

You can trigger the workflow manually here: [Workflow URL](actions/workflows/dispatch.yml)

## Usage Example

You can trigger the workflow manually or call it from another workflow.

Workflow Dispatch URL
URL: https://github.com/hmanzur/repo-bundler-py/actions/workflows/blank.yml

## 🚀 Purpose

This repository defines a manual GitHub Actions workflow (`workflow_dispatch`) that:

- Clones a target Python application repository
- Automatically computes a version string from Git metadata
- Bundles the codebase into a distributable archive
- Publishes the archive as a GitHub Actions artifact

It's designed to support CI pipelines that need consistent versioned artifacts, especially during early integration setups.

## 🎓 Used In

This workflow is part of the [SoftServe PeEx program](https://peex.softserveinc.com) and is being used to build and version artifacts from:

👉 [edonosotti/ci-cd-tutorial-sample-app](https://github.com/edonosotti/ci-cd-tutorial-sample-app)

## Inputs

| Name            | Description                               | Required       | Default                                      |
|-----------------|-------------------------------------------|----------      |------------------------------------          |
| `repo`          | Repository to clone (in `owner/repo` format)    | ✅       | `edonosotti/ci-cd-tutorial-sample-app` |
| `ref`           | Git reference to checkout (branch, tag, or SHA) | ✅       | `main`                                 |
| `python_version`| Python version to use in the workflow           | ❌       | `3.8`                                  |


## How it works

1. Clones the specified repository and ref.

2. Creates a Python virtual environment.

3. Installs dependencies.

4. Runs database migrations.

5. Runs unit tests.

6. Computes a version string based on git tags.

7. Packages the project into a tarball artifact.

8. Uploads the artifact to GitHub Actions.

## References

- [Reusing workflows - GitHub Docs](https://docs.github.com/en/actions/using-workflows/reusing-workflows)

- [Workflow dispatch - GitHub Docs](https://docs.github.com/en/actions/using-workflows/events-that-trigger-workflows#workflow_dispatch)