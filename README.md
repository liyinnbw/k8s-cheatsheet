# k8s-cheatsheet

## Namespace

Create new namespace
```
kubectl create ns <new-name-space>
```

List all namespaces on the cluster
```
kubectl get ns
```

Delete namespace & everything under it
```
kubectl delete ns <new-name-space>
```

## Deployment

Create new deployment from yaml file
```
kubectl create -f deployment.yml
```

List deployments under namespace
```
# simple listing
kubectl -n <namespace> get deployments
# list & show labels
kubectl -n <namespace> get deployments --show-labels
# filter by labels
kubectl -n <namespace> get deployments -l label1=value1,label2=value2
```

Delete deployment with yaml file used to create them
```
kubectl delete -f deployment.yml
```

