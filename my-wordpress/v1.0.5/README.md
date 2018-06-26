# WordPress

[LaboConnect](https://laboconnect.com/) is a medical application. This template is in developement phase
It has to be used by non-docker/kubernetes users ! Team did his best to limit interaction with console...

## Before doing anything
In order to deploy an application, you'll have to pull containers images from a [private registry] (https://docker-01.progi.loc:5000/). This means that you need credentials. So the point is to verify that you have the good secret on your machine. First access the USERS Settings and pick the user specs. Then type the following command :

``` console
$ kubectl get secret --all-namespaces
```

The things below doesn't match with LaboConnect deployment

## Introduction


## Installing the Chart

To install the chart with the release name `my-release`:

> **Tip**: List all releases using `helm list`

| Parameter                            | Description                                | Default                                                    |
| ------------------------------------ | ------------------------------------------ | ---------------------------------------------------------- |
| `image.registry`                     | WordPress image registry                   | `docker.io`                                                |
| `image.repository`                   | WordPress image name                       | `bitnami/wordpress`                                        |
| `smtpProtocol`                       | SMTP protocol [`tls`, `ssl`]               | `nil`                                                      |
| `mariadb.enabled`                    | Deploy MariaDB container(s)                | `true`                                                     |
| `mariadb.mariadbRootPassword`        | MariaDB admin password                     | `nil`                                                      |
| `mariadb.mariadbDatabase`            | Database name to create                    | `bitnami_wordpress`                                        |
| `mariadb.mariadbUser`                | Database user to create                    | `bn_wordpress`                                             |
| `mariadb.mariadbPassword`            | Password for the database                  | _random 10 character long alphanumeric string_             |
| `externalDatabase.host`              | Host of the external database              | `localhost`                                                |
| `externalDatabase.user`              | Existing username in the external db       | `bn_wordpress`                                             |
| `externalDatabase.password`          | Password for the above username            | `nil`                                                      |
| `externalDatabase.database`          | Name of the existing database              | `bitnami_wordpress`                                        |
| `externalDatabase.port`              | Database port number                       | `3306`                                                     |
| `serviceType`                        | Kubernetes Service type                    | `LoadBalancer`                                             |
| `nodePorts.https`                    | Kubernetes https node port                 | `""`                                                       |
| `healthcheckHttps`                   | Use https for liveliness and readiness     | `false`                                                    |
| `ingress.enabled`                    | Enable ingress controller resource         | `false`                                                    |
| `ingress.hosts[0].name`              | Hostname to your WordPress installation    | `wordpress.local`                                          |
| `ingress.hosts[0].path`              | Path within the url structure              | `/`                                                        |
| `ingress.hosts[0].tls`               | Utilize TLS backend in ingress             | `false`                                                    |
| `ingress.hosts[0].tlsSecret`         | TLS Secret (certificates)                  | `wordpress.local-tls-secret`                               |
| `ingress.hosts[0].annotations`       | Annotations for this host's ingress record | `[]`                                                       |
| `persistence.enabled`                | Enable persistence using PVC               | `true`                                                     |
| `persistence.storageClass`           | PVC Storage Class                          | `nil` (uses alpha storage class annotation)                |
| `persistence.accessMode`             | PVC Access Mode                            | `ReadWriteOnce`                                            |
| `persistence.size`                   | PVC Storage Request                        | `10Gi`                                                     |
| `nodeSelector`                       | Node labels for pod assignment             | `{}`                                                       |

The above parameters map to the env variables defined in [bitnami/wordpress](http://github.com/bitnami/bitnami-docker-wordpress). For more information please refer to the [bitnami/wordpress](http://github.com/bitnami/bitnami-docker-wordpress) image documentation.
