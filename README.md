# gtctl

## Overview

gtctl is a command-line tool for managing GreptimeDB cluster. gtctl integrates the multiple operations in one binary.

## Getting Started

### Prerequisites

- Kubernetes 1.18 or higher version is required

  You can use [kind](https://kind.sigs.k8s.io/) to create your own Kubernetes cluster:

  ```
  $ kind create cluster
  ```
### Usage

- Download gtctl release

  Get latest gtctl from [our release
  page](https://github.com/GreptimeTeam/gtctl/releases).

- Get gtctl version

  ```
  $ gtctl version
  ```

- Create GreptimeDB cluster

  ```
  $ gtctl create cluster db_name -n your_namespace
  ```

- Get GreptimeDB cluster

  ```
  $ gtctl get cluster db_name -n your_namespace
  ```

- Get All GreptimeDB clusters

  ```
  $ gtctl get clusters
  ```

- Scale GreptimeDB cluster

  ```
  # Scale datanode to 3 replicas.
  $ gtctl scale cluster db_name -n your_namespace -c datanode --replicas 3

  # Scale frontend to 5 replicas.
  $ gtctl scale cluster db_name -n your_namespace -c frontend --replicas 5
  ```

- Delete GreptimeDB cluster

  ```
  # Delete GreptimeDB cluster.
  $ gtctl delete cluster db_name -n your_namespace

  # Delete GreptimeDB cluster, including etcd cluster.
  $ gtctl delete cluster db_name -n your_namespace --tear-down-etcd
  ```

## Development

Just make it:

```
$ make
```