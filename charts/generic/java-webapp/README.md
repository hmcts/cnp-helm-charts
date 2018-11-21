# Generic Microservice

## Example configuration
```
environment:
  POSTGRES_HOST: localhost
  POSTGRES_SSL_MODE: disable
  POSTGRES_DATABASE: rhubarb
postgres:
  enabled: true
  config:
    POSTGRES_HOST: localhost
    POSTGRES_USER: hmcts
    POSTGRES_PASSWORD: hmcts
    POSTGRES_DB: rhubarb
```

## Configuration

The following table lists the configurable parameters of the java-webapp chart and their default values.

| Parameter                               | Description                                                                                  | Default                                     |
| --------------------------------------- | -------------------------------------------------------------------------------------------- | ------------------------------------------- |
| `applicationPort`                  | The port your app runs on in its container                                                                 | `8080`                                       |
| `image`                        | Full image url, i.e hmcts.azurecr.io/hmcts/cnp-rhubarb-recipes-service:pr-110                                                                       | `nil`                                 |
| `environment`                      | A map containing all environment values you wish to set                                                                           | `nil`                           |
| `configmap`                             | A config map, can be used for environment specific config                                                                            | `{VERSION}`                                 |
| `memoryRequests`                      | Requests for memory                                                                            | `512Mi`                                    |
| `cpuRequests`                     | Requests for cpu                                                                   | `200m`                                       |
| `memoryLimits`                           | Memory limits                                                               | `512Mi`                                      |
| `cpuLimits`                        | CPU limits                                                     | `200m`                                       |
| `postgres.enabled`                   | Enables a postgres container                                                                       | `false`           |
| `postgres.image`                       | Image for the postgres container                                                                          | `postgres:10-alpine`                                       |
| `postgres.config`                       | Environment variables for the postgres container                                                                 | `nil`           |
| `ingressHost`                       | Host for ingress controller to map the container to                                                                           | `nil (but set by pipeline)`                                       |
| `serviceName`                     | Name of this webapp i.e. rhubarb-recipes-service                                                     | `nil (but set by pipeline)`                                      |
