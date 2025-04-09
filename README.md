
# Go-API Infra

Infrastructe for Go-API repository. Using helm and Kubernetes




## Pre-requisites (for macOS)

Install minikube and helm



```bash
  brew install minikube

  brew install helm

  kubectl create secret docker-registry docker-hub-secret \
  --docker-server=https://index.docker.io/v1/ \
  --docker-username=<your-docker-username> \
  --docker-password=<your-docker-password> \
  --docker-email=<your-email>
```

You will need a docker-registry secret so minikube is able to pull the image from the registry

## Run Locally

Clone the project

```bash
  helm install go-api-release ./go-api-chart
  minikube tunnel
  curl localhost:8080
```

```bash
  helm repo add prometheus-community https:prometheus-community.github.io/helm-charts

  helm repo update

  helm install kube-prometheus-stack \
  --create-namespace \
  --namespace kube-prometheus-stack \
  prometheus-community/kube-prometheus-stack
```

