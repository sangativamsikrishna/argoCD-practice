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


Some important commands to get the pods, service and secret details of the argocd in the namespace argocd
```bash
kubectl get pods -n argocd

```bash
kubectl get svc -n argocd

```bash
kubectl get secret -n argocd

To do the port forward in order to access from our local host here with the mapping of local host:127.0.0.1 with any port like 8080 to the argocd-server service port 443 here,  the command is
```bash
kubectl port-forward svc/argocd-server -n argocd 8080:443

Also here we want to access this in our local host like ArgoC UI with the url: https://localhost:8080

The username is deafult admin and password you can get from this command and want to decode base64 from the google or any terminal as base64 decode is not available in the local cmd here

The command to get the decode password is

```bash
kubectl get secret argocd-initial-admin-secret -n argocd -o jsonpath="{.data.password}" 

