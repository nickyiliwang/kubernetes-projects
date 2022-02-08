# kubectl (alias to k)
- only tool we need to talk to Kubernetes
- ~/.kube/config file
  - K8s API addresses
  - path to TLS certificates to authenticate
- --kubeconfig flag to pass a config file, or directly with --server, --user

## k get
k get node/no/nodes

outputs:
k get node -o wide
k get no -o yaml

with jq:
k get nodes -o json | 
jq ".items[] | {name:.metadata.name} + .status.capacity" > filename.json

## get services
Service is an abstraction which defines a logical set of Pods and a policy by which to access them

k get services/svc

## get pods
closest thing to getting all running containers

k get pods

## Namespaces
segregation of resources, filter
use cases: deploy same app multiple times separated by namespaces, permission control, network policies control  

-n/--namespaces can be used with most k commands

k get namespaces/ns

k get pods --all

k get pods --all-namespaces

### kube-system
in an fresh environment like mine, kube-system namespaces will show
all of the parts that makes up the K8s control plane,
such as etcd, coredns, apiserver, controller, scheduler ...

<net name> is not shown, but it is the optional(per node) component managing the network overlay

### Other namespaces
kube-public: 
- created by installer and used for security bootstrapping (gives us data on how to connect, like the certificates)
- ConfigMap named cluster-info, you can get this by doing: k -n kube-public get configmaps
- Select and output in yaml: k -n kube-public get configmaps cluster-info -o yaml => reveals info like certificates

kube-node-lease:
- it's there by default, leave it alone

## k describe
more ways to get extra info from outputs

k describe <type>/<name>

## types and definitions
list all available resource types:
k api-resources

define a type:
k explain <type>

view a specific field (introspection documentation):
k explain node.spec

list of all fields and subfields:
k explain node --recursive