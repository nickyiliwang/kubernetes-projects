# Starting a simple pod with kubectl run
k run used to create:
1. Deployment(with deployment spec) => ReplicaSet => Pod => Container 

## Deployment, Replica Set, Pod, Container
Deployment:
- allows scaling, rolling updates, rollbacks
- multi-deployments for a canary deployment
- delegates pods management to replica sets

Replica set:
- makes sure that a given number of identical pods are running
- allows scaling
- rarely used directly

*kubectl run is now similar to docker run. 
It creates a single pod, where docker run creates a single container.

To do this now, use: 
k create deployment <deployment name> --image <image name> -- <commands>
k create deployment pingpong --image alpine -- ping 1.1.1.1