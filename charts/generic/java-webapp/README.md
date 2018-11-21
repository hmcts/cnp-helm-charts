# Generic Microservice
```
applicationPort: 8080
environment:
  POSTGRES_HOST: localhost
  POSTGRES_SSL_MODE: disable
  POSTGRES_DATABASE: rhubarb
configmap:
  POSTGRES_HOST: localhost
  POSTGRES_SSL_MODE: disable
  POSTGRES_DATABASE: rhubarb
postgres:
  enabled: true
  image: postgres:10-alpine
  config:
    POSTGRES_HOST: localhost
    POSTGRES_USER: hmcts
    POSTGRES_PASSWORD: hmcts
    POSTGRES_DB: hmcts
    
# Don't modify below here
serviceName: ${SERVICE_NAME}
image: ${IMAGE_NAME}
ingress:
  host: ${SERVICE_FQDN}
```