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

| Parameter               | Description                         | Default                      |
|-------------------------|-------------------------------------|------------------------------|
| `db.dsn`                | DataSource Name                     | `file:/data/ha.db?_journal=WAL&_timeout=5000&_sync=NORMAL` |
| `db.concurrent_queries` | Number of concurrent queries        | `50`                         |
| `db.extensions`         | List of SQLite extensions to load   | ``                           |
| `log_level`             | Log level (info, warn, error, debug)| `info`                       |  
| `nats.enabled`          | Enable/disable embedded NATS server | `true`                       |
| `nats.logs`             | Show embedded NATS logs             | `false`                      |
| `nats.user`             | Embedded NATS username              | ``                           |
| `nats.pass`             | Embedded NATS password              | ``                           |
| `nats.config`           | Override default NATS config        | see values.yaml              |
| `pgwire.enabled`        | Enable/disable Postgres Wire server | `true`                       |
| `pgwire.user`           | PostgreSQL Wire Porocol username    | `ha`                         |
| `pgwire.pass`           | PostgreSQL Wire Porocol password    | `ha`                         |
| `pgwire.cert`           | PostgreSQL Wire Porocol certificate | ``                           |
| `pgwire.key`           | PostgreSQL Wire Porocol certificate key | ``                        |
| `replicaCount`          | Number of instances                 | `3`                          |
| `relication.max_age`    | Replication stream max age          | `24h`                        |
| `relication.stream`     | Replication stream name             | `ha_replication`              |
| `relication.timeout`    | Replication publisher timeout       | `15s`                        |
| `relication.url`        | URL to connect to external NATS for replication | ``               |
| `storage.size`          | Storage size                        | `10Gi`                       |
| `storage.className`     | Storage class name                  | `standard`                   |
| `stream.replicas`       | Number of stream replicas           | `1`                          |