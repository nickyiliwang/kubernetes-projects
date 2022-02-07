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
1. Vanilla upstream: un-opinionated install, harder but customizable
2. Cloud-managed: EKS ...
3. Self-Managed: Docker Enterprise, Rancher ...
4. Vanilla installers: kubeadm ...
5. Local: minikube ...

