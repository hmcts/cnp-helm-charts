# NodeJS Microservice Helm Chart

## Configuration
| Parameter          | Description                             | Default     |
|--------------------|-----------------------------------------|-------------|
|`applicationPort`   |The port the application is listening on |3000         |
|`environment`       |Map of environment variables             |none         |
|`cpuRequests`       |Minimum CPU required                     |200m         |
|`cpuLimits`         |Maximum CPU limit                        |500m         |
|`memoryRequests`    |Minimum Memory required                  |64Mi         |
|`memoryLimits`      |Maximum Memory limit                     |256Mi        | 

## Example `values.yaml` for Pipeline
```
applicationPort: 1337
environment:
  MY_ENV_VAR_1: my_value_1
  MY_ENV_VAR_2: my_value_2

# Don't modify below here
namespace: ${NAMESPACE}
serviceName: ${SERVICE_NAME}
image: ${IMAGE_NAME}
ingressHost: ${SERVICE_FQDN}
```

## Example `values.yaml` for Testing on Sandbox
```
applicationPort: 1337
environment:
  RECIPE_BACKEND_URL: http://rhubarb-recipe-backend-saat.service.core-compute-saat.internal

namespace: my-namespace
serviceName: my-service
image: hmctssandbox.azurecr.io/hmcts/custard-frontend
ingressHost: custard-helm.service.core-compute-saat.internal
```

## Install on Sandbox
First configure your Helm client according to the [docs](https://docs.microsoft.com/en-us/azure/container-registry/container-registry-helm-repos#add-a-repository-to-helm-client).

Then to install:
```
helm install --name custard-helm hmctssandbox/nodejs-app -f values.yaml
```

## Clean up
```
helm delete --purge custard-helm
```
