# PocketBase HA Helm Chart

[PocketBase HA](http://github.com/litesql/pocketbase-ha) is an highly available leaderless PocketBase cluster powered by go-ha database/sql driver.

## Features

- High Availability: Run multiple PocketBase instances in a leaderless cluster.
- Replication: Synchronize data across nodes using NATS.
- Embedded or External NATS: Choose between an embedded NATS server or an external one for replication.

## Get Repo Info

```console
helm repo add litesql https://litesql.github.io/helm-charts
helm repo update
```

_See [helm repo](https://helm.sh/docs/helm/helm_repo/) for command documentation._

## Installing the Chart

To install the chart with the release name `my-release`:

```console
helm install my-release litesql/pocketbase-ha
```

## Uninstalling the Chart

To uninstall/delete the my-release deployment:

```console
helm delete my-release
```

The command removes all the Kubernetes components associated with the chart and deletes the release.

## Configuration

| Parameter               | Description                                     | Default          |
|-------------------------|-------------------------------------------------|------------------|
| `nats.config`           | NATS config file                                | see values.yaml  |
| `nats.stream`           | NATS stream name                                | `pb`             |
| `replicaCount`          | Number of instances                             | `3`              |
| `relication.url`        | URL to connect to external NATS for replication | ``               |
| `storage.size`          | Storage size                                    | `10Gi`           |
| `storage.className`     | Storage class name                              | `standard`       |
| `stream.replicas`       | Number of stream replicas                       | `1`              |