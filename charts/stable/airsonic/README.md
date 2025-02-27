# airsonic

![Version: 6.4.2](https://img.shields.io/badge/Version-6.4.2-informational?style=flat-square) ![AppVersion: 10.6.2](https://img.shields.io/badge/AppVersion-10.6.2-informational?style=flat-square)

Airsonic is a Free and Open Source community driven media server

**This chart is not maintained by the upstream project and any issues with the chart should be raised [here](https://github.com/bjw-s/charts/issues/new/choose)**

## Source Code

* <https://github.com/airsonic-advanced/airsonic-advanced>
* <https://github.com/bjw-s/charts/tree/master/charts/airsonic>

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
helm install airsonic bjw-s/airsonic
```

## Installing the Chart

To install the chart with the release name `airsonic`

```console
helm install airsonic bjw-s/airsonic
```

## Uninstalling the Chart

To uninstall the `airsonic` deployment

```console
helm uninstall airsonic
```

The command removes all the Kubernetes components associated with the chart **including persistent volumes** and deletes the release.

## Configuration

Read through the [values.yaml](./values.yaml) file. It has several commented out suggested values.
Other values may be used from the [values.yaml](https://github.com/bjw-s/library-charts/tree/main/charts/stable/common/values.yaml) from the [common library](https://github.com/bjw-s/library-charts/tree/main/charts/stable/common).

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

```console
helm install airsonic \
  --set env.TZ="America/New York" \
    bjw-s/airsonic
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart.

```console
helm install airsonic bjw-s/airsonic -f values.yaml
```

## Custom configuration

If you plan to use networked storage to store your media or config for Airsonic, (NFS, etc.) please take a look at the
Fast Access option in the Airsonic settings. This will help improve the performance of the application
by not constantly monitoring media folders.

## Values

**Important**: When deploying an application Helm chart you can add more values from our common library chart [here](https://github.com/bjw-s/library-charts/tree/main/charts/stable/common)

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| enableServiceLinks | bool | `false` | Enable Kubernetes service links. Disabled by default, since AIRSONIC_* environment vars potentially clash with the application. |
| env | object | See below | environment variables. |
| env.CONTEXT_PATH | string | `nil` | Used to set the base path for reverse proxies eg. /airsonic, /music, etc. |
| env.JAVA_OPTS | string | `nil` | For passing additional java options. For some reverse proxies, you may need to pass `JAVA_OPTS=-Dserver.use-forward-headers=true` for airsonic to generate the proper URL schemes. |
| env.TZ | string | `"UTC"` | Set the container timezone |
| image.pullPolicy | string | `"IfNotPresent"` | image pull policy |
| image.repository | string | `"airsonicadvanced/airsonic-advanced"` | image repository |
| image.tag | string | `"latest@sha256:f7cbafac28063dce99b443037547b4fe40ae270b7bc5e47efea9bb5d6751ca9d"` | image tag The specific digest is for the `amd64` image, but arm compatible images are also available. |
| ingress.main | object | See values.yaml | Enable and configure ingress settings for the chart under this key. |
| persistence | object | See values.yaml | Configure persistence settings for the chart under this key. |
| probes | object | See values.yaml | Configures the probes for the main Pod. |
| service | object | See values.yaml | Configures service settings for the chart. Normally this does not need to be modified. |

## Changelog

### Version 6.4.2

#### Added

N/A

#### Changed

* Upgraded `common` chart dependency to version 1.5.0

#### Fixed

N/A

### Older versions

A historical overview of changes can be found on [ArtifactHUB](https://artifacthub.io/packages/helm/bjw-s/airsonic?modal=changelog)

## Support

- See the [Docs](https://docs.bjw-s.com/our-helm-charts/getting-started/)
- Open an [issue](https://github.com/bjw-s/charts/issues/new/choose)
- Ask a [question](https://github.com/bjw-s/organization/discussions)
- Join our [Discord](https://discord.gg/sTMX7Vh) community

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v0.1.1](https://github.com/bjw-s/helm-docs/releases/v0.1.1)
