# Kubernetes

<details>
<summary>Notes</summary>

* Components -
  * API Server
    1. acts as a front-end for kubernetes
  * etcd
    1. key value store
    2. implements logs
  * kubelet
    1. runs on each node
    2. makes sure that the containers are running as expected
  * container runtime
    1. used to run containers
  * controller
  * scheduler
    1. distibutes work across multiple nodes

* master node has `kube-apiserver` & worker nodes have `kubelet` agent
* `kubelet` agent interacts with the master node
* master node contains `kube-apiserver`, `etcd`, `controller`, `scheduler`

</details>

<details>
<summary>Commands</summary>

```kubectl
kubectl cluster-info
```

```kubectl
kubectl get nodes
```

deploy a pod `<pod-name>` (default image is from docker hub) -

```kubectl
kubectl run <pod-name> --image <image>
```

```kubectl
kubectl create -f <yml-file>
```

get all pods -

```kubectl
kubectl get pods
```

describe pod -

```kubectl
kubectl describe pod <pod-name>
```

</details>
