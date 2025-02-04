# omejdn-server

# To install DAPS 1.7.1 version, follow below steps:- 

git clone -b fetaure/dapsUpgrade https://github.com/catenax-ng/product-DAPS.git


helm install dapsName helmchartDirectory/  -n NameSpace


![Version: 0.1.0](https://img.shields.io/badge/Version-0.1.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 1.0.0](https://img.shields.io/badge/AppVersion-1.0.0-informational?style=flat-square)

DAPS server helm-chart

Omejdn is a minimal but extensible OAuth 2.0/OpenID connect server used for ...

IoT devices which use their private keys to request OAuth2 access tokens in order to access protected resources
Websites or apps which retrieve user attributes
It is used as the Dynamic Attribute Provisioning Service (DAPS) prototype of the Industrial Data Space.

Some of Omejdn's core features include:

Database-free easy-to-read configuration files
Integration of existing LDAP directory services
Fully configurable through the Admin API Plugin
A User Selfservice API Plugin
Standard Compliance (see below)
IMPORTANT: Omejdn is meant to be a research sandbox in which we can (re)implement standard protocols and potentially extend and modify functionality under the hood to support research projects. Use at your own risk! At a minimum, take a look at the documentation for production setups.


## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` | Pod affinity configuration |
| autoscaling | object | `{"enabled":false, "maxReplicas":100, "minReplicas":1, "targetCPUUtilizationPercentage":80}` | DAPS autoscaling configuration |
| env.config | object | `{}` | Additional env variables |
| env.secret | object | `{}` | Additional env variables that should be stored in encrypted way |
| fullnameOverride | string | `""` |  |
| image.pullPolicy | string | `"IfNotPresent"` | Image pull policy |
| image.repository | string | `"nginx"` | DAPS docker image |
| image.tag | string | `""` | Image tag. Overrides the image tag whose default is the chart appVersion. |
| imagePullSecrets | list | `[]` | Secret which contains dockerconfig.json from private container registry with daps image |
| ingress.annotations | object | `{}` | Additional ingress annotations |
| ingress.enabled | bool | `false` | If set to `true`, DAPS will be exposed with ingress controller at http(s)://(ingress.host)/(ingress.pathPrefix) |
| ingress.host | string | `"chart-example.local"` |  |
| ingress.pathPrefix | string | `"/"` | Path prefix to be added to DAPS URI. Regex can be used |
| ingress.rootPath | string | `"/"` | Root prefix without regex rules that used to configure daps host name in configuration |
| ingress.tls.certMgr.enabled | bool | `false` | If `true` cert-manager will be used to issue a certificate with ingress.host CN name |
| ingress.tls.certMgr.issuer | string | `""` | Cert-manager issuer name |
| ingress.tls.enabled | bool | `false` | If `true` daps will be exposed with https |
| nameOverride | string | `""` |  |
| nodeSelector | object | `{}` | Node selection configuration |
| omejdn.createDefaultAdmin | bool | `false` | Default user and client will be created if set to `true`. User credentials set in `omejdn.defaultAdminUser` section |
| omejdn.defaultAdminUser | string | `"admin:admin"` | Default user credentials in format `user:password` |
| omejdn.serverKey | string | `""` | Server key content. DAPS will generate key if it's not provided at startup |
| omejdn.serverKeyFolderPath | string | `"/opt/server-key"` | Path to directory with private server key |
| persistence.enabled | bool | `true` | If `true` persistent volume will be used to store clients and users configuration |
| persistence.storageClass | string | `"azurefile"` | Storage class to claim a volume. |
| persistence.storageSize | string | `"1Gi"` | Volume size |
| podAnnotations | object | `{}` |  |
| podSecurityContext | object | `{}` | Pod security context configuration |
| replicaCount | int | `1` | DAPS instances count |
| resources | object | `{}` | Pod resources requests and limits configuration |
| securityContext | object | `{}` | Pod security context configuration |
| service.port | int | `4567` | Service port |
| service.type | string | `"ClusterIP"` | Service type |
| serviceAccount.annotations | object | `{}` | Annotations to add to the service account |
| serviceAccount.create | bool | `true` | Specifies whether a service account should be created |
| serviceAccount.name | string | `""` | The name of the service account to use. -- If not set and create is true, a name is generated using the fullname template |
| tolerations | list | `[]` | Pod toleration settings |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.5.0](https://github.com/norwoodj/helm-docs/releases/v1.5.0)
