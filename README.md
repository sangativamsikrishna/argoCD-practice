# argoCD-practice
This repo is used to test the minikube from my local system.

Hello here I am giving the reference of the ArgoCD deployment of a sample application here with the following commands here

1. Install ArgoCD  with some requirements of having

kubernetes cluster and kubectl installed in your system here

2. Now Install the ArgoCD herwe with the following comands here
    Create the Namespca  argocd here 
```bash
kubectl create namespace -n argocd
```
The Insall the ArgoCD with manifest.yml file here with the command here

```bash
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
