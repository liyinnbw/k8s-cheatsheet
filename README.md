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

Get namespace resource quota
```
kubectl -n <namespace> get resourcequota
# OR describe for more detail
kubectl -n <namespace> describe resourcequota <resource quoate name>
```

Delete namespace & everything under it
```
kubectl delete ns <new-name-space>
```

Switch default namespace to avoid -n <namespace> all the time
```
kubectl config set-context --current --namespace=<namespace>
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

Get a deployment by yaml file
```
kubectl get -f deployment.yml
# OR describe for more detail
kubectl describe -f deployment.yml
```

Update deployment
```
kubectl apply -f new-deployment.yml
```

Delete deployment
```
# by yaml file used to create it
kubectl delete -f deployment.yml
# by name
kubectl delete deployment <deployment name>
```

## Service
List services under namespace
```
kubectl -n <namespace> get svc
```

Get a service by name
```
kubectl get svc <service name>
# OR describe for more detail
kubectl describe svc <service name>
```

Delete a service under a namespace by name
```
kubectl -n <namespace> delete svc <service name>
```

## ConfigMap

Create new config map from yaml file
```
kubectl create -f configmap.yaml
```

List config maps under namespace
```
kubectl -n <namespace> get cm
```

Get a specific config map under namespace
```
kubectl -n <namespace> get cm <configmap name>
# OR describe for more detail
kubectl -n <namespace> describe cm <configmap name>
```

Delete config map
```
# by yaml file used to create it
kubectl delete -f configmap.yml
# by name
kubectl delete cm <configmap name>
```

## Pod

Get into a pod interactively
```
kubectl -n <namespace> exec -it <pod> -- bash
```

View pod logs
```
kubectl -n <namespace> logs <pod>
```

List pod environment variables
```
kubectl -n <namespace> exec <pod> env
```

## Ingress

Create new ingress from yaml file
```
kubectl create -f ingress.yml
```

List ingress under namespace
```
kubectl -n <namespace> get ing
```
