# Ha Helm Chart

## Get Repo Info

```console
helm repo add litesql https://litesql.github.io/helm-charts
helm repo update
```

_See [helm repo](https://helm.sh/docs/helm/helm_repo/) for command documentation._

## Installing the Chart

To install the chart with the release name `my-release`:

```console
helm install my-release litesql/ha
```

## Uninstalling the Chart

To uninstall/delete the my-release deployment:

```console
helm delete my-release
```

The command removes all the Kubernetes components associated with the chart and deletes the release.

## Configuration

| Parameter             | Description                  | Default                      |
|-----------------------|------------------------------|------------------------------|
| `replicaCount`        | Number of nodes              | `3`                          |
| `storage.size`        | Storage size                 | `10Gi`                       |
| `storage.className`   | Storage class name           | `standard`                   |
| `stream.replicas`     | Number of stream replicas    | `1`                          |
| `nats.logs`           | Show embedded NATS logs      | `false`                      |
| `nats.config`         | Override default NATS config | see values.yaml              |
