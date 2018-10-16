# Generic Microservice
```
applicationPort: 8080
environment:
  POSTGRES_HOST: localhost
  POSTGRES_SSL_MODE: disable
  POSTGRES_DATABASE: rhubarb
resources:
  requests:
    memory: "512Mi"
    cpu: "200m"
  limits:
    memory: "1024Mi"
    cpu: "2500m"
configmap:
  POSTGRES_HOST: localhost
  POSTGRES_SSL_MODE: disable
  POSTGRES_DATABASE: rhubarb
  
# Don't modify below here
serviceName: ${SERVICE_NAME}
image: ${IMAGE_NAME}
ingress:
  host: ${SERVICE_FQDN}
```