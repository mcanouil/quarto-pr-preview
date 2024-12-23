# Quarto Pull Request Preview

This repository contains a Quarto website project with GitHub Actions for deployment and preview.

## GitHub Actions

### Deploy Action

The `deploy.yml` workflow is triggered on pushes to the `main` branch.
It builds and deploys the Quarto website to GitHub Pages via the `gh-pages` branch.

- **Workflow file**: [`.github/workflows/deploy.yml`](.github/workflows/deploy.yml)
- **Triggers**:
  - Push to `main` branch
  - Manual dispatch
- **Steps**:
  1. Checkout the repository
  2. Setup Quarto
  3. Render the Quarto project
  4. Publish the site to GitHub Pages

### Preview Action

The `preview.yml` workflow is triggered by comments on pull requests or manually.
It generates a preview of the Quarto website for the pull request.

- **Workflow file**: [`.github/workflows/preview.yml`](.github/workflows/preview.yml)
- **Triggers**:
  - Comment `/preview` on a pull request
  - Manual dispatch
- **Steps**:
  1. Checkout the pull request branch
  2. Setup Quarto
  3. Render the Quarto project with the preview profile
  4. Update the preview directory on GitHub Pages
  5. Post a comment with the preview URL

## Usage

To deploy the site manually, trigger the `Deploy` workflow from the Actions tab.

To generate a preview for a pull request, comment `/preview` on the pull request.

## License

This project is licensed under the MIT License.
