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
* [kubectl Usage Conventions](https://kubernetes.io/docs/reference/kubectl/conventions/)

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

extract pod definiton file from already created pod-

```kubectl
kubectl get pod <pod-name> -o yaml > pod-definition.yaml
```

Here are some of the commonly used formats:

`-o jsonOutput` a JSON formatted API object.

`-o namePrint` only the resource name and nothing else.

`-o wideOutput` in the plain-text format with any additional information.

`-o yamlOutput` a YAML formatted API object.

```kubectl
kubectl [command] [TYPE] [NAME] -o <output_format>
```

Create a configMap

```kubectl
kubectl create configmap webapp-config-map --from-literal=APP_COLOR=darkblue
```

Getuser of pod

```kubectl
kubectl exec ubuntu-sleeper -- whoami
```

</details>
