This repo contains:

- a "hello world" flask app (python)
- a Dockerfile to set up the runtime environment
- a deployment.yaml file for k8s to deploy the container image into pods

How to run this k8s locally (tested on Mac):

Prerequisites
1. install minikube so you can run a local kubernetes cluster
https://minikube.sigs.k8s.io/

2. install kubernetes
https://kubernetes.io/docs/tasks/tools/install-kubectl-macos/

Operations
1. Spin up pods locally:
```
eval $(minikube docker-env) # configure shell for minikube's docker daemon
minikube start # ensure that minikube cluster is running locally
kubectl apply -f deployment.yaml # deploy
kubectl get pods # verify
minikube service flask-app-service # run
```

2. Spin down pods locally:
```
kubectl delete deployments --all
```
