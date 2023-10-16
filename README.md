# openapi-configmap

This project and the following commands have been tested using [minikube](https://minikube.sigs.k8s.io/docs/start/).

## kubectl

```sh
kubectl create configmap openapi-kubectl --from-file=openapi-configmap/petstore-minimal.json

kubectl get configmap -o yaml openapi-kubectl
```

## Helm

> NOTE: using Helm requires the file to base64 encoded via the templating process

### Template

```sh
helm template openapi-configmap
```

### Install

```sh
helm upgrade --install openapi-configmap ./openapi-configmap

kubectl get configmap openapi -o yaml
```
