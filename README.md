# What is this?
A simple template for techincal documentation using Sphinx with a slightly customized Read the Docs theme and a standard way to publish to an Azure Static Web App using GitHub Actions.

# How to use it?
Just edit `conf.py` and customize as you please. Make sure to change `CHANGEME` entries to whatever you like.

## Publishing to Azure Static Web App (SWA)
If you have an Azure subscription and would like to publish your documentation, a simple way is to publish it to SWA, which can easily serve the HTML output.
A GitHub workflow is included, and once you have added a SWA in Azure and connected it to your GitHub account, you can use the included workflow to handle building the HTML from the RST.
Make sure to change the `secrets.AZURE_STATIC_WEB_APPS_API_TOKEN` in the included `.github/workflows/azure-static-web-app.yaml` to whatever Azure creates for that particular SWA typically something like `secrets.AZURE_STATIC_WEB_APPS_API_TOKEN_RED_AIRPLANE_055C16903`.

### Authentication
By default I've included a [`routes.json`](https://docs.microsoft.com/en-us/azure/static-web-apps/routes) which will require authentication from Azure AD in order to view the documentation. If the documentation is meant to be completely public, remove the `Copy routes.json` step from the yaml-file.