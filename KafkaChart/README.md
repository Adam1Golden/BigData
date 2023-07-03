# CLuster Configuration
## General
| Parameter | Description | Default | Type |
| --------- | ----------- | ------- | ---- |
| `namespace` | namespace to deploy cluster | nil | string |
| `clusterName` | cluster name | nil | string |

## Kafka
| Parameter | Description | Default | Type |
| --------- | ----------- | ------- | ---- |
| `kafka.replicas` | amount of kafka brokers | int |
| `kafka.storage.type` | storage type - Ephemeral, Persistent, JBOD | jbod | string |
| `kafka.externalPort` | external port - exposing the brokers with load balancer. | 9094 | int |
### Storage configurations
#### ephemeral
```
...
kafka:
  ...
  storage:
    type: ephemeral
```
#### persistent-claim
```
...
kafka:
  ...
  storage:
    type: persistent-claim
    size: 2Gi
    deleteClaim: false
```
#### jbod
```
...
kafka:
    ...
    storage:
      type: jbod
      volumes:
      - id: 0
        type: persistent-claim
        size: 100Gi
        deleteClaim: false
      - id: 1
        type: persistent-claim
        size: 100Gi
        deleteClaim: false
      - id: 2
        type: persistent-claim
        size: 100Gi
        deleteClaim: false
```
| Parameter | Description | Default | Type |
| --------- | ----------- | ------- | ---- |
| `kafka.storage.volume.type` | type of volume storage | persistent-claim | string |
| `kafka.storage.volume.size` | storage size | 2Gi | string |
| `kafka.storage.volume.deleteClaim` | boolean. determine to delete the storage after deleting cluster | false | string |

## Zookeeper
| Parameter | Description | Default | Type |
| --------- | ----------- | ------- | ---- |
| `zookeeper.replicas` | amount of kafka brokers | int |
| `zookeeper.storage.type` | storage type - Ephemeral, Persistent, JBOD | jbod | string |
| `zookeeper.storage.size` | storage size | 2Gi | string |
| `zookeeper.storage.volume.deleteClaim` | boolean. determine to delete the storage after deleting cluster | false | string |
| `zookeeper.externalPort` | external port - exposing the brokers with load balancer. | 9094 | int |

## Topics
| Parameter | Description | Default | Type |
| --------- | ----------- | ------- | ---- |
| `topic.name` | name of the topic | nil | string |
| `topic.partitions` | partitions amount fot the topics | nil | int |
| `topics.replicas` | replicas amount fot the topics | nil | int |

* The topics are stored as an array.
* In order to add/delete topic add/delete it to/from the array and upgrade your helm repo.
