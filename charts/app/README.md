# app

![Version: 1.0.0](https://img.shields.io/badge/Version-1.0.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 1.0.0](https://img.shields.io/badge/AppVersion-1.0.0-informational?style=flat-square)

Common Web application Helm Chart

## Values

| Key                                            | Type   | Default                                              | Description                                                                   |
|------------------------------------------------|--------|------------------------------------------------------|-------------------------------------------------------------------------------|
| affinity                                       | object | `{}`                                                 |                                                                               |
| app.env                                        | object | `{}`                                                 | Environment variables required for application (will be referenced to Secret) |
| app.host                                       | string | `"127.0.0.1"`                                        |                                                                               |
| app.name                                       | string | `"nodejs"`                                           |                                                                               |
| app.port                                       | int    | `5000`                                               |                                                                               |
| app.workingDir                                 | string | `""`                                                 |                                                                               |
| configMaps                                     | list   | `[]`                                                 | Names of existing external secrets to use. Optionals for safety               |
| fullnameOverride                               | string | `""`                                                 |                                                                               |
| image                                          | string | `"dcr.bndigital.dev/library/nodejs:1.0.0"`           |                                                                               |
| imagePullPolicy                                | string | `"Always"`                                           |                                                                               |
| imagePullSecrets                               | list   | `[]`                                                 |                                                                               |
| imageRegistry                                  | object | `{}`                                                 |                                                                               |
| ingress.annotations                            | object | `{}`                                                 |                                                                               |
| ingress.className                              | string | `"nginx"`                                            |                                                                               |
| ingress.fallbackHost                           | string | `""`                                                 |                                                                               |
| ingress.host                                   | string | `""`                                                 |                                                                               |
| ingress.path                                   | string | `"/"`                                                |                                                                               |
| ingress.pathType                               | string | `"Prefix"`                                           |                                                                               |
| ingress.proxy.backend.port                     | int    | `80`                                                 |                                                                               |
| ingress.proxy.backend.service                  | string | `"{{ printf \"%s-%s\" .Release.Name .Chart.Name }}"` |                                                                               |
| ingress.proxy.enabled                          | bool   | `false`                                              |                                                                               |
| ingress.proxy.implementation                   | string | `"graphql"`                                          |                                                                               |
| ingress.proxy.path                             | string | `""`                                                 |                                                                               |
| ingress.proxy.pathType                         | string | `"ImplementationSpecific"`                           |                                                                               |
| ingress.proxy.templates.api.path               | string | `"/api"`                                             |                                                                               |
| ingress.proxy.templates.api.pathType           | string | `"Prefix"`                                           |                                                                               |
| ingress.proxy.templates.graphql.path           | string | `"/graphql"`                                         |                                                                               |
| ingress.proxy.templates.graphql.pathType       | string | `"Exact"`                                            |                                                                               |
| ingress.proxy.templates.strapi.path            | string | `"/(admin                                            | auth                                                                          |import-export-content|callback|connect|content-manager|content-type-builder|graphql|email|email-designer|entity-relationship-chart|i18n|register|responsive-image|users-permissions|upload|uploads)(.*)"` |  |
| ingress.proxy.templates.strapi.pathType        | string | `"ImplementationSpecific"`                           |                                                                               |
| ingress.secretName                             | string | `""`                                                 |                                                                               |
| ingress.tls.enabled                            | bool   | `true`                                               |                                                                               |
| ingress.tls.issuer.email                       | string | `"email@test.com"`                                   |                                                                               |
| ingress.tls.issuer.enabled                     | bool   | `false`                                              |                                                                               |
| ingress.tls.issuer.name                        | string | `"letsencrypt"`                                      |                                                                               |
| ingress.tls.issuer.server                      | string | `"https://acme-v02.api.letsencrypt.org/directory"`   |                                                                               |
| ingress.uploadSize                             | string | `"5m"`                                               |                                                                               |
| initContainers                                 | string | `nil`                                                |                                                                               |
| livenessProbe.enabled                          | bool   | `true`                                               |                                                                               |
| nameOverride                                   | string | `""`                                                 |                                                                               |
| nodeSelector                                   | object | `{}`                                                 |                                                                               |
| podAnnotations."app.kubernetes.io/environment" | string | `"production"`                                       |                                                                               |
| podSecurityContext.fsGroup                     | int    | `1000`                                               |                                                                               |
| podSecurityContext.fsUser                      | int    | `1000`                                               |                                                                               |
| podSecurityContext.runAsNonRoot                | bool   | `true`                                               |                                                                               |
| priorityClassName                              | string | `""`                                                 |                                                                               |
| readinessProbe.enabled                         | bool   | `true`                                               |                                                                               |
| replicaCount                                   | int    | `1`                                                  |                                                                               |
| resources                                      | object | `{}`                                                 |                                                                               |
| secrets                                        | list   | `[]`                                                 | Names of existing external secrets to use. Optionals for safety               |
| securityContext                                | object | `{}`                                                 |                                                                               |
| service.name                                   | string | `"http"`                                             |                                                                               |
| service.port                                   | int    | `80`                                                 |                                                                               |
| service.type                                   | string | `"ClusterIP"`                                        |                                                                               |
| serviceAccount.create                          | bool   | `false`                                              |                                                                               |
| serviceAccount.name                            | string | `""`                                                 |                                                                               |
| startupProbe.enabled                           | bool   | `true`                                               |                                                                               |
| tolerations                                    | list   | `[]`                                                 |                                                                               |
| volumes                                        | list   | `[]`                                                 |                                                                               |
| autoscaling.enabled                            | bool   | `false`                                              | Enable or disable Horizontal Pod Autoscaling                                  |
| autoscaling.minReplicas                        | int    | `1`                                                  | Minimum number of replicas for autoscaling                                    |
| autoscaling.maxReplicas                        | int    | `5`                                                  | Maximum number of replicas for autoscaling                                    |
| autoscaling.targetCPUUtilizationPercentage     | int    | `90`                                                 | Target CPU utilization percentage for autoscaling                             |
| autoscaling.targetMemoryUtilizationPercentage  | int    | `90`                                                 | Target memory utilization percentage for autoscaling                          |


----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.5.0](https://github.com/norwoodj/helm-docs/releases/v1.5.0)
