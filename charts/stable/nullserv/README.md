# nullserv

![Version: 2.4.2](https://img.shields.io/badge/Version-2.4.2-informational?style=flat-square) ![AppVersion: 1.3.0](https://img.shields.io/badge/AppVersion-1.3.0-informational?style=flat-square)

A simple null file http and https server

**This chart is not maintained by the upstream project and any issues with the chart should be raised [here](https://github.com/bjw-s/charts/issues/new/choose)**

## Source Code

* <https://github.com/bmrzycki/nullserv>

## Requirements

Kubernetes: `>=1.16.0-0`

## Dependencies

| Repository | Name | Version |
|------------|------|---------|
| https://bjw-s.github.io/helm-charts | common | 1.5.0 |

## TL;DR

```console
helm repo add bjw-s https://bjw-s.github.io/helm-charts/
helm repo update
helm install nullserv bjw-s/nullserv
```

## Installing the Chart

To install the chart with the release name `nullserv`

```console
helm install nullserv bjw-s/nullserv
```

## Uninstalling the Chart

To uninstall the `nullserv` deployment

```console
helm uninstall nullserv
```

The command removes all the Kubernetes components associated with the chart **including persistent volumes** and deletes the release.

## Configuration

Read through the [values.yaml](./values.yaml) file. It has several commented out suggested values.
Other values may be used from the [values.yaml](https://github.com/bjw-s/library-charts/tree/main/charts/stable/common/values.yaml) from the [common library](https://github.com/bjw-s/library-charts/tree/main/charts/stable/common).

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

```console
helm install nullserv \
  --set env.TZ="America/New York" \
    bjw-s/nullserv
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart.

```console
helm install nullserv bjw-s/nullserv -f values.yaml
```

## Custom configuration

N/A

## Values

**Important**: When deploying an application Helm chart you can add more values from our common library chart [here](https://github.com/bjw-s/library-charts/tree/main/charts/stable/common)

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| controller.replicas | int | `2` | Number of pods to load balance between |
| env | object | See below | environment variables. See more environment variables in the [nullserv documentation](https://github.com/bmrzycki/nullserv/blob/master/README.md). |
| env.TZ | string | `"UTC"` | Set the container timezone |
| image.pullPolicy | string | `"IfNotPresent"` | image pull policy |
| image.repository | string | `"ghcr.io/bjw-s/nullserv"` | image repository |
| image.tag | string | `"v1.3.0"` | image tag |
| ingress.main | object | See values.yaml | Enable and configure ingress settings for the chart under this key. |
| probes | object | See values.yaml | Configures the probes for the main Pod. |
| service | object | See values.yaml | Configures service settings for the chart. |

## Changelog

### Version 2.4.2

#### Added

N/A

#### Changed

* Upgraded `common` chart dependency to version 1.5.0

#### Fixed

N/A

### Older versions

A historical overview of changes can be found on [ArtifactHUB](https://artifacthub.io/packages/helm/bjw-s/nullserv?modal=changelog)

## Support

- See the [Docs](https://docs.bjw-s.com/our-helm-charts/getting-started/)
- Open an [issue](https://github.com/bjw-s/charts/issues/new/choose)
- Ask a [question](https://github.com/bjw-s/organization/discussions)
- Join our [Discord](https://discord.gg/sTMX7Vh) community

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v0.1.1](https://github.com/bjw-s/helm-docs/releases/v0.1.1)
