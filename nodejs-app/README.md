# NodeJS Microservice
```
applicationPort: 8080
environment:
resources:
  requests:
    memory: "512Mi"
    cpu: "200m"
  limits:
    memory: "1024Mi"
    cpu: "2500m"
configmap:
  
# Don't modify below here
serviceName: ${SERVICE_NAME}
image: ${IMAGE_NAME}
ingress:
  host: ${SERVICE_FQDN}
```