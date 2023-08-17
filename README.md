# k8s-list-pods-example

## Running environment
Kubernetes on Docker Desktop for Mac.

## Description
Four resources will be created by applying the yaml: A service account that will be used by the pod; A role grants the permission to get and list pods in default namespace; A rolebinding to attach the role to the service account; And a pod that lists all pods running under default namespace by curl.

## Commands
Create the pod and the required service account, role, and rolebinding
```shell
kubectl apply -f curl-list-pods.yaml
```

Get the logs of the pod, it should print out the response from API server containting all pods under `default` namesapece.
```shell
kubectl logs curl-list-pods
```

Clean up all created resources
```shell
kubectl delete -f curl-list-pods.yaml
```
