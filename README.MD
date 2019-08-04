# K8s Stuff

## Basic Knowledge

### Big Picture

An orchestrator for Microservice Apps.

## Kubectl

It is a command line tool that translate manifest files (YAML) in commands and queries communicating directly with the `kube-apiserver` in the master nodes.

## Masters

The Kubernetes Control Plane

### kube-apiserver

It is a Front-end and API (REST) that receices and processes k8s commands. These commands are in JSON format and are consumed via manifest files (descriptors).

### Cluster Store

It is a persistent storage that keeps the cluster state and configs. It uses `etcd` as KV database.

### kube-controller-manager

Controller of controller:

- Node controller
- Endpoints controller
- Namespace controller

Watches for changes and try to ensure that the desired state.

### kube-scheduler

Watches apiserver for new pods. Assigns work to nodes based on:

- affinity rules
- constraints
- resources

## Nodes

Are the minion nodes. The responsible for the actual workload.

### Kubelet

- The main Kubernetes agent
- Register node with cluster
- Watches apiserver
- Instantiates pods
- Reports back to master
- Exposes endpoint on `10255` port

### Container Engine

Does container management:

- Pulling images
- Starting/stopping containers

Plugable. It is usually Docker. Can be rkt.

### kube-proxy

Kubernetes networking:

- Pod IP addresses
  - All containers in a pode share a single IP
