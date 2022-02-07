# What and why of orchestration
What:
Making many servers to act like one, and run many containers

Major container orchestration projects:
K8s, Swarm, ECS, HashiCorp Nomad ...

## Rise of Docker
Docker allowed us to package apps and distribute them across machines, even through HTTP protocols, and had a common runtime that allowed many different copies of the same app on a single OS
Faster replacement and getting more out of a machine

## Container orchestrator
1. schedule running of containers on servers
2. dispatch them across many nodes
3. health checks and reactions
4. storage, networking, proxy, security, and logging features
5. **declarative rather than imperative
6. Customization with an API layer

## Kubernetes distributions
List of certified distros (adhere to K8s API guidelines)
<!-- https://www.cncf.io/certification/software-conformance/ -->
1. Vanilla upstream: un-opinionated install, harder but customizable
2. Cloud-managed: EKS ...
3. Self-Managed: Docker Enterprise, Rancher ...
4. Vanilla installers: kubeadm ...
5. Local: Docker Desktop, minikube ...
6. Special: Rancher K3s

## K8s simple infrastructure
[Simple Diagram](diagrams/K8s-Simple-Infra.png)
[Alternative view](diagrams/K8s-Simple-infra-2.png)
- Nodes consists:
  - Container runtime/engine: ie. Docker
  - kublet: node agent, comm with API
  - Kube-proxy = needed for networking, but not enough
- Control plane x 1:
  - API Server(Inbound & Outbound): Heart and soul of K8s, comm between agents on the nodes(Kubelet)
  - [etcd](https://etcd.io/): key-value store db for config, app run instructions
  - Core Services:
    - Controller Manager
    - Scheduler
  - CoreDNS: services in your orchestrator

## K8s API and Resource types
K8s APIs are RESTful mostly
Common resource types:
1. node (machine, physical or virtual in the cluster)
2. pod (group of containers running together in the node)
3. service (network end point that connects to one or multiple containers)

## Pods
1. Abstraction
2. can be multiple containers, usually one
3. Smallest deployable unit
4. K8s can't manage containers direcltly
5. IP addresses are associated with pods, not containers
6. containers in a pod can 
    a. share localhost and comm bewteen containers
    b. share volumes
7. Docker doesn't know pods, only containers/namespaces/volumes


