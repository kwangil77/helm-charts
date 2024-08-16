# steampipe

A Helm chart for Kubernetes to deploy Steampipe

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| kwangil77 | <kwangil77@hotmail.com> | <https://github.com/kwangil77> |

## Prerequisites

* Helm 3+

## Add repository

```console
helm repo add kwangil77 https://kwangil77.github.io/helm-charts
helm repo update
```

## Install Helm chart (repository mode)

```console
helm install [RELEASE_NAME] steampipe/kwangil77
```

This install all the Kubernetes components associated with the chart and creates the release.

_See [helm install](https://helm.sh/docs/helm/helm_install/) for command documentation._

## Uninstall Helm chart

```console
helm uninstall [RELEASE_NAME]
```

This removes all the Kubernetes components associated with the chart and deletes the release.

_See [helm uninstall](https://helm.sh/docs/helm/helm_uninstall/) for command documentation._

## Configuration

See [Customizing the chart before installing](https://helm.sh/docs/intro/using_helm/#customizing-the-chart-before-installing). To see all configurable options with comments:

```console
helm show values steampipe/kwangil77
```

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` | Affinity for pod assignment |
| args | list | `["--foreground","--show-password"]` | Arguments for Pod |
| service | object | `{"listen":"network","port":9193,"annotations":{},"type":"ClusterIP"}` | Configure service for Steampipe |
| command | list | `[]` | Command for Pod |
| deploymentAnnotations | object | `{}` | Deployment annotations |
| env | list | `[{"name":"STEAMPIPE_LOG_LEVEL","value":"TRACE"}]` | Environment variables to configure application |
| envFrom | list | `[]` | Variables from file |
| extraConfig | object | `{"configMaps":{"config":[{"data":{"openshift.spc":"connection \"openshift\" {\n  plugin      = \"openshift\"\n  config_path = \"~/.kube/config\"\n}\n"},"name":"openshift-connection","type":"Opaque"}],"enabled":false},"secrets":{"config":[{"data":{"azure.spc":"connection \"azure\" {\n  plugin          = \"azure\"\n  environment     = \"AZUREPUBLICCLOUD\"\n  tenant_id       = \"00000000-0000-0000-0000-000000000000\"\n  subscription_id = \"00000000-0000-0000-0000-000000000000\"\n  client_id       = \"00000000-0000-0000-0000-000000000000\"\n  client_secret   = \"~dummy@3password\"\n}\n"},"name":"azure-connection","type":"Opaque"},{"data":{"config":"current-context: federal-context\napiVersion: v1\nclusters:\n- cluster:\n    certificate-authority: path/to/my/cafile\n    server: https://horse.org:4443\n  name: horse-cluster\ncontexts:\n- context:\n    cluster: horse-cluster\n    namespace: chisel-ns\n    user: green-user\n  name: federal-context\nkind: Config\nusers:\n- name: green-user\n  user:\n    client-certificate: path/to/my/client/cert\n    client-key: path/to/my/client/key\n"},"name":"openshift-kubeconfig","type":"Opaque"}],"enabled":false}}` | Extra configuration for Steampipe |
| extraContainers | list | `[]` | Extra containers to add to the pod |
| extraObjects | list | `[]` | Extra Kubernetes manifests to deploy |
| extraVolumeMount | list | `[]` | Mount extra volumes |
| extraVolumes | list | `[]` | Reference volumes |
| fullnameOverride | string | `""` | String to fully override steampipe.fullname template |
| image | object | `{"pullPolicy":"IfNotPresent","repository":"turbot/steampipe","tag":""}` | Image registry |
| imagePullSecrets | list | `[]` | Registry secret names as an array |
| initContainer | object | `{"extraInitVolumeMount":[],"image":{"pullPolicy":"IfNotPresent","repository":"turbot/steampipe","tag":""},"mods":[],"plugins":[],"resources":{},"securityContext":{"runAsNonRoot":true,"runAsUser":9193}}` | Configure initContainers |
| initContainer.plugins | list | `[]` | Configure Steampipe plugins Ref: https://hub.steampipe.io/plugins |
| initContainer.resources | object | `{}` | The resources limits and requested |
| livenessProbe | object | `{}` | Configure liveness Ref: https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-startup-probes/#define-startup-probes |
| nameOverride | string | `""` | String to partially override steampipe.fullname template (will maintain the release name) |
| nodeSelector | object | `{}` | Node labels for pod assignment |
| podAnnotations | object | `{}` | Pod annotations |
| podSecurityContext | object | `{"fsGroup":9193,"runAsGroup":65534,"runAsUser":9193}` | Privilege and access control settings for a Pod or Container |
| readinessProbe | object | `{}` | Configure readinessProbe Ref: https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-startup-probes/#define-startup-probes |
| replicaCount | int | `1` | Number of replicas |
| resources | object | `{}` | The resources limits and requested |
| securityContext | object | `{"runAsNonRoot":true,"runAsUser":9193}` | Privilege and access control settings |
| serviceAccount | object | `{"annotations":{},"automountServiceAccountToken":false,"create":true,"name":""}` | Enable creation of ServiceAccount |
| startupProbe | object | `{}` | Configure startupProbe Ref: https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-startup-probes/#define-startup-probes |
| tolerations | list | `[]` | Tolerations for pod assignment |
