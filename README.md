# kube-microservices-example

This repository contains experiments on building a microservice platform over
[Kubernetes]. The goal of this repository is to build a platform, where
the engineers responsible for delivering business value can focus on that 
purpose while the cross cutting concerns of the environment are left for the
team responsible for managing this platform. This encompasses the cross-cutting
concerns of operating such a platform as an internal service:

- identity management
- authentication and authorization
- network communication management (retries / failovers)
- API gateway for API management
- observability

## Base setup

### Hardware

The hardware running the benchmarks is a 2017 15" Macbook Pro with a Core i7
quad-core processor at 2.9GHz and 16 GB RAM on MacOS 11.1.

### Kubernetes

The setup is running [minikube] on Docker using the following command: 

```shell script
minikube start \
    --memory=8192 \
    --cpus=4 \
    --driver=docker \
    --container-runtime=docker \
    --kubernetes-version=v1.20.0
```

### Demo application

The demo application used in this setup is the Istio Bookstore (v1.8.1)
application. For consistency, the sample 
[bookinfo.yaml](apps/bookinfo/bookinfo.yaml) containing the exact specification
is downloaded and stored in the `apps` directory.


[Kubernetes]: https://kubernetes.io/
[minikube]: https://minikube.sigs.k8s.io/docs/