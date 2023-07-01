# [`namesilo-dyndns`]()

> A Helm chart for windsting999/namesilo-dyndns (https://hub.docker.com/r/windsting999/namesilo-dyndns)

[![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ]()[![Version: 0.1.0](https://img.shields.io/badge/Version-0.1.0-informational?style=flat-square) ]()[![AppVersion: 1.16.0](https://img.shields.io/badge/AppVersion-1.16.0-informational?style=flat-square) ]()

* <https://hub.docker.com/r/windsting999/namesilo-dyndns>

## Requirements

- [`helm`](https://helm.sh) - Refer to their [docs](https://helm.sh/docs) to get started.

## Usage

To use this chart add the repo as follows:

```sh
helm repo add namesilo-dyndns https://grapemix.github.io/namesilo-dyndns/
```

If you had already added this repo earlier, run `helm repo update` to retrieve the latest versions of the packages.

To install this chart simply run the following command:

```sh
helm install namesilo-dyndns grapemix/namesilo-dyndns
```

To uninstall this chart simply run the following command:

```sh
helm delete namesilo-dyndns
```

## Values

The following values can be used to adjust the helm chart.

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` |  |
| autoscaling.enabled | bool | `false` |  |
| autoscaling.maxReplicas | int | `1` |  |
| autoscaling.minReplicas | int | `1` |  |
| cronJob.annotations | object | `{}` | Additional annotations for the cronjob object. |
| cronJob.enabled | bool | `false` | Create a cron job to update the DNS zone. |
| cronJob.failedJobsHistoryLimit | int | `1` | The number of failed finished jobs to retain. |
| cronJob.labels | object | `{}` | Additional labels for the cronjob object. |
| cronJob.nameservers | list | `[]` | The nameservers used to resolve ip service domain. Leave empty to inherit from cluster/node. |
| cronJob.schedule | string | `"30 * * * *"` | Update schedule for the cron job. |
| cronJob.successfulJobsHistoryLimit | int | `3` | The number of successful finished jobs to retain. |
| cronJob.suspend | bool | `false` | Enable/disable the cron job schedule quickly. |
| env[0] | object | `{"name":"TZ","value":"UTC"}` | Timezone for the container. |
| env[1].name | string | `"PRINT_SAME_COUNT_STEP"` |  |
| env[1].value | int | `360` |  |
| fullnameOverride | string | `"namesilo-dyndns"` |  |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.repository | string | `"grapemix/namesilo-dyndns"` |  |
| image.tag | string | `"0.1"` |  |
| nodeSelector | object | `{}` |  |
| replicaCount | int | `1` |  |
| resources.limits.cpu | string | `"10m"` |  |
| resources.limits.memory | string | `"16Mi"` |  |
| resources.requests.cpu | string | `"10m"` |  |
| resources.requests.memory | string | `"16Mi"` |  |
| secret.annotations | object | `{}` | Additional annotations for the secret object. |
| secret.create | bool | `true` | Create a new secret containing the token. |
| secret.existingSecret | string | `""` | Use an existing secret to store the token. |
| secret.labels | object | `{}` | Additional labels for the secret object. |
| secret.token | string | `""` | Token used when not using an existing secret. |
| tolerations | list | `[]` |  |

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| grapemix |  |  |

## License

[GPL v3](../LICENSE.md)
