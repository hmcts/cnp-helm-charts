# CNP Helm Charts
## Overview
Azure Container Registry can now be used as a Helm repository: https://docs.microsoft.com/en-gb/azure/container-registry/container-registry-helm-repos

## Purpose
Using a generic Helm chart to install applications has the following benefits:
* Able to update chart in one place and changes would propagate to all teams using it
* Enforce important configuration (e.g. resource limits)
* Less YAML config for teams to maintain.  Only need to contribute `values.yaml`
* Teams can create their own charts
* Easy cleanup (e.g. `helm delete`).  Could go back to team namespaces.

## Adding a new chart
Send a PR with your chart, if your team will be maintaining it then update the [CODEOWNERS](.github/CODEOWNERS) file with either your name or your team name.
