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

## Expose GRPC service

### minikube

```sh
minikube service openapi-deployment --url
```

You should see somthing like...

```sh
http://127.0.0.1:53357
❗  Because you are using a Docker driver on darwin, the terminal needs to be open to run it.
```

Interact with the GRPC API using [gRPC UI](https://github.com/fullstorydev/grpcui)...

```sh
grpcui --plaintext 127.0.0.1:53357
```

A new browser window should spin up for the gRPC Web UI allowing you to inetract with the service.
