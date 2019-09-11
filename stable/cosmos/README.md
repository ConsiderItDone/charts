# Cosmos

[Cosmos](https://cosmos.network) is a decentralized network of independent parallel blockchains, each powered by BFT consensus algorithms like Tendermint consensus

## TL;DR;

```console
$ helm install stable/cosmos
```

## Configuration

The following table lists the configurable parameters of the Drupal chart and their default values.

| Parameter                         | Description                                | Default                                                   |
| --------------------------------- | ------------------------------------------ | --------------------------------------------------------- |
| `image.registry`                  | Cosmos image registry                      | `docker.io`                                               |
| `image.repository`                | Cosmos Image name                          | `tendermint/gaia`                                          |
| `image.tag`                       | Cosmos Image tag                           | `v0.34.7`                                              |
| `image.pullPolicy`                | Cosmos image pull policy                   | `IfNotPresent`                                            |
| `nameOverride`                    | String to partially override cosmos.fullname template with a string (will prepend the release name) | `nil` |
| `fullnameOverride`                | String to fully override cosmos.fullname template with a string                                     | `nil` |
| `service.type`                    | Kubernetes Service type                    | `LoadBalancer`                                            |
| `service.port`                    | Service HTTP port                          | `80`                                                      |
| `service.httpsPort`               | Service HTTPS port                         | `443`                                                     |
| `service.externalTrafficPolicy`   | Enable client source IP preservation       | `Cluster`                                                 |
| `service.nodePorts.http`          | Kubernetes http node port                  | `""`                                                      |
| `service.nodePorts.https`         | Kubernetes https node port                 | `""`                                                      |
| `persistence.enabled`             | Enable persistence using PVC               | `true`                                                    |
| `persistence.storageClass` | PVC Storage Class for Cosmos volume        | `nil` (uses alpha storage class annotation)               |
| `persistence.accessMode`   | PVC Access Mode for Cosmos volume          | `ReadWriteOnce`                                           |
| `persistence.existingClaim`| An Existing PVC name                       | `nil`                                                     |
| `persistence.size`         | PVC Storage Request for Cosmos volume      | `100Gi`                                                     |
| `cosmos.genesisPath`       | Genesis Json file path                     | `https://raw.githubusercontent.com/cosmos/launch/master/genesis.json` |
| `cosmos.base.proxyApp`         | TCP or UNIX socket address of the ABCI application | `tcp://127.0.0.1:26658`|
| `cosmos.base.moniker`         | A custom human readable name for this node | ``|
| `cosmos.base.fastSync`         | If this node is many blocks behind the tip of the chain, FastSync allows them to catchup quickly by downloading blocks in parallel and verifying their commits | `true`|
| `cosmos.base.dbBackend`         | Database backend: leveldb or memdb or cleveldb | `leveldb`|
| `cosmos.base.dbPath`         | Database directory | `data`|
| `cosmos.p2p.seeds`         | Comma separated list of seed nodes to connect to | `3e16af0cead27979...`  (taken from https://github.com/cosmos/launch/)|