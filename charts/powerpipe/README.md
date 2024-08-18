# powerpipe

A Helm chart for Kubernetes to deploy Powerpipe

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
helm install [RELEASE_NAME] powerpipe/kwangil77
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
helm show values powerpipe/powerpipe
```

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` | Affinity for pod assignment |
| args | list | `[]` | Arguments for Pod |
| service | object | `{"listen":"network","port":9033,"annotations":{},"type":"ClusterIP"}` | Configure service for powerpipe |
| command | list | `[]` | Command for Pod |
| deploymentAnnotations | object | `{}` | Deployment annotations |
| env | list | `[{"name":"POWERPIPE_LOG_LEVEL","value":"TRACE"}]` | Environment variables to configure application |
| envFrom | list | `[]` | Variables from file |
| extraConfig | object | `{}` | Extra configuration for powerpipe |
| extraContainers | list | `[]` | Extra containers to add to the pod |
| extraObjects | list | `[]` | Extra Kubernetes manifests to deploy |
| extraVolumeMount | list | `[]` | Mount extra volumes |
| extraVolumes | list | `[]` | Reference volumes |
| fullnameOverride | string | `""` | String to fully override powerpipe.fullname template |
| image | object | `{"pullPolicy":"IfNotPresent","repository":"turbot/powerpipe","tag":""}` | Image registry |
| imagePullSecrets | list | `[]` | Registry secret names as an array |
| ingress | object | `{"annotations":{},"className":"","enabled":false,"hosts":[{"host":"chart-example.local","paths":[{"path":"/","pathType":"ImplementationSpecific"}]}],"tls":[]}` | Ingress configuration to expose app |
| initContainer | object | `{"extraInitVolumeMount":[],"image":{"pullPolicy":"IfNotPresent","repository":"turbot/powerpipe","tag":""},"mods":[],"plugins":[],"resources":{},"securityContext":{"runAsNonRoot":true,"runAsUser":9193}}` | Configure initContainers |
| initContainer.mods | list | `[]` | Configure powerpipe mods Ref: https://hub.powerpipe.io/mods |
| initContainer.resources | object | `{}` | The resources limits and requested |
| livenessProbe | object | `{}` | Configure liveness Ref: https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-startup-probes/#define-startup-probes |
| nameOverride | string | `""` | String to partially override powerpipe.fullname template (will maintain the release name) |
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
