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
* [Persistent Volumes](https://kubernetes.io/docs/concepts/storage/persistent-volumes/#claims-as-volumes)

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

Get user of pod

```kubectl
kubectl exec ubuntu-sleeper -- whoami
```

label a node

```kubectl
kubectl label node node01 color=blue
```

logs of container inside a pod

```kubectl
kubectl logs webapp-2 -c simple-webapp
```

metric server

```kubectl
git clone https://github.com/kodekloudhub/kubernetes-metrics-server.git
cd kubernetes-metrics-server/
kubectl create -f .
kubectl top node
kubectl top pod
```

match labels and get the pod

```kubectl
kubectl get pods --selector env=dev
```

match labels and get the pod, no headers will remove the header and wc -l will give the count

```kubectl
kubectl get pods --selector bu=finance --no-headers | wc -l
```

```kubectl
kubectl get all --all-namespaces
```

Get ingress resources in all namespaces

```kubectl
kubectl get ingress --all-namespaces
```

Get context of kubeconfig, here `my-kube-config` is the file name 

```kubectl
kubectl config current-context --kubeconfig my-kube-config
```

Set context of kubeconfig, here `my-kube-config` is the file name and `research` is the context defined in kubeconfig

```kubectl
kubectl config --kubeconfig=/root/my-kube-config use-context research
```

Can check if the user has access to get the pods

```kubectl
kubectl get pods --as dev-user
```

</details>
