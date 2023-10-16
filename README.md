# openapi-configmap

## kubectl

```sh
kubectl create configmap openapi --from-file=openapi-configmap/petstore-minimal.json

kubectl get configmap -o yaml openapi
```

## Helm

### Template

```sh
helm template openapi-configmap
```

### Install

```sh
helm upgrade --install openapi-configmap ./openapi-configmap

kubectl get configmap openapi -o yaml
```
