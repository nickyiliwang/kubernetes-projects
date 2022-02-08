# kubernetes-projects
This is a collection of all my kubernetes projects

[basics](0.basics/basics.md)
[kubectl commands](0.basics/kubectl-cmd.md)

## Util commands:
1st window, attach:

kubectl attach --namespace=shpod -ti shpod

2nd window, create a new bash shell:

kubectl exec --namespace=shpod -ti shpod -- bash -l

