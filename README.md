# resume with GitHub Actions auto release workflow

This repo contains LaTeX source code of my resume, as well as CI/CD workflows in GitHub Actions that compile it to PDF, upload to Azure Blob Storage, and upload to GitHub releases.

## How it works

First, create the Azure credentials and store it in this GitHub repo's **Settings -> Secrets and variables -> Actions**.
- Secret name `AZURE_CREDENTIALS`: Paste the JSON object as value. See `.github/workflows/README.md` for details.
- Secret name `AZURE_STORAGE_ACCOUNT`: Paste the storage account UUID from Azure Portal.
- Secret name `AZURE_STORAGE_CONTAINER`: Paste the storage container name from Azure Portal.

Then, any code push or pull request merge on `main` branch will trigger the GitHub Actions workflow, besides manual triggering.
- Output file `fan_jin_resume.pdf` is the normal version of my resume. It explains my work professionally.
- Output file `fan_jin_resume_easy_version.pdf` is the easy version of my resume. It explains my job duties and is user friendly to visa officers.

Finally, both versions of PDF output file will be uploaded to my Azure storage container. They are also released here with tag name the current timestamp (e.g. `20240929T050651Z`).

## Credits to

- latex-moderncv (LaTeX template): https://github.com/mliu7/latex-moderncv
- GitHub Actions workflow xu-cheng/latex-action: https://github.com/xu-cheng/latex-action
- Official GitHub Actions workflows [azure/login@v1](https://github.com/Azure/login), [azure/CLI@v1](https://github.com/Azure/cli), [actions/create-release@v1](https://github.com/actions/create-release), [actions/upload-release-asset@v1](https://github.com/actions/upload-release-asset).
