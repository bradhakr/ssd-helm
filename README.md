## SSD Helm Charts
This repository contains Helm Chart for Self Services Demo Application.

## Usage
Helm Charts are essentially 'packaged applications' that describe how the SSD application shall be built in a Kubernetes cluster. Navigate into the Chart and review the values.yaml for more details

## Quick Start

Add the SSD-Chart repository:

    $ helm repo add ssd-chart https://bradhakr.github.io/ssd-helm/
    $ helm repo update
    $ helm repo list
    
Retrieve Values.yaml locally

    $ helm inspect values ssd-chart/ssd > values.yaml

## Install this Chart
Then, you can install the charts by:

    $ helm install <<release name>> <<chart-name>> -n <<namespace>> -f <<localtion of values.yaml>>
 
## Upgrade this Chart
To upgrade the SSD deployment

    $ helm upgrade <<release name>> -n <<namespace>> -f <<localtion of values.yaml>>

## delete this installation
To delete the SSD deployment

 
    $ helm delete <release name> -n <release namespace>
 

## Note
This Helm Chart was created by Balaji Radhakrishnan.

All Chart configurations referenced on this repository and documentation are in <i>values.yaml</i>. The base values represent the minimum configuration required to run each application, they can be overriden with your own <i>my-values.yaml<i> file.

## Custom values
To make sure that your custom values don't get overwritten by a pull, create your own values.yaml (myvalues.yaml..) then specify -f myvalues.yaml when deploying/upgrading

## Configuration
The following table lists the configurable parameters of the Gateway chart and their default values. See values.yaml for additional parameters and info

| Parameter                        | Description                               | Default                                                      |
| -----------------------------    | -----------------------------------       | -----------------------------------------------------------  |
| `service.type`                | Service Type   | `ClusterIP` |
| `service.port`                      | Service Port                       | `443`                                                     |
| `service.targetPort`          | Service TargetPort | `8443`  |
  | `deployment.replicaCount`          | Deployment Replica Count | `1`  |
  | `deployment.image.repoName`          | Image Name| `us-docker.pkg.dev/demos-esd-security-balaji/dockerimages/sspgw-webapp`  |
  | `deployment.image.tag`          | Image Tag Information | `v1.0`  |
   | `ingress.enabled`          | Image Tag Information | `true`  |
   | `ingress.host`          | Host Name | `nil`  |
   | `ingress.secretName`          | Secret Name | `nil`  |
   | `ingress.class`          | Ingress Class | `nginx`  |
   | `ingress.issuer`          | Issure Name | `lets-encrypt`  |
   | `appSecretTLS.create`          | create of secret | `false`  |
   | `appSecretTLS.secretName`          | Secret Name | `webapp-ssd-tls`  |
   | `appSecretTLS.host`          | Host Information | `nil`  |
  | `appSecretTLS.cert`          | base64 Certificate | `Enclosed selfSigned `  |
 | `appSecretTLS.key`          | base64 Key | `Enclosed selfSigned`  |

