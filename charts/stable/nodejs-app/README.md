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

## Example `values.yaml`
```
applicationPort: 1337
environment:
  MY_ENV_VAR_1: my_value_1
  MY_ENV_VAR_2: my_value_2

# Don't modify below here
namesapce: ${NAMESPACE}
serviceName: ${SERVICE_NAME}
image: ${IMAGE_NAME}
ingressHost: ${SERVICE_FQDN}
```