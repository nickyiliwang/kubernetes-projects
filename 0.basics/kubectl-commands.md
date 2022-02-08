# kubectl
- only tool we need to talk to Kubernetes
- ~/.kube/config file
  - K8s API addresses
  - path to TLS certificates to authenticate
- --kubeconfig flag to pass a config file, or directly with --server, --user

## kubectl get
kubectl get node/no/nodes

outputs:
kubectl get node -o wide
kubectl get no -o yaml

with jq:
kubectl get nodes -o json | 
jq ".items[] | {name:.metadata.name} + .status.capacity" > filename.json

## kubectl describe
more ways to get extra info from outputs

kubectl describe <type>/<name>

## types and definitions
list all available resource types:
kubectl api-resources

define a type:
kubectl explain <type>

view a specific field:
kubectl explain node.spec

list of all fields and subfields:
kubectl explain node --recursive