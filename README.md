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

## Releasing a chart
NOTE: This is temporary until we have an automated CI based release process

For now:
1. Configure the hmcts repo as the default ACR `az configure --defaults acr=hmcts`
2. Log in to ACR `az acr helm repo add  --subscription 1c4f0704-a29e-403d-b719-b90c34ef14c9`
3. Run the helm package command `helm package charts/generic/java-webapp/`
4. Push the created tarball to ACR `az acr helm push java-webapp-0.0.5.tgz --subscription 1c4f0704-a29e-403d-b719-b90c34ef14c9`
5. You may wish to cleanup the generated tar ball (it is git ignored, so won't be committed) `rm *.tgz`

You can then search the helm chart repo to see the updated version `helm search hmcts/java-webapp`