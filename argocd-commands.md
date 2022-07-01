## Install Argo CD
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

## Download Argo CD CLI

brew install argocd

## Access The Argo CD API Server

kubectl patch svc argocd-server -n argocd -p '{"spec": {"type": "LoadBalancer"}}'


## check all pods in the argocd namespace

kubectl get pods -n argocd

## check all services in the argocd namespace

kubectl get svc -n argocd

## access argocd-server which hosts the dashboard

kubectl port-forward -n argocd svc/argocd-server 8080:80

## Access localhost:8080


## login with credentials 

Username: admin
Get the secret from argocd-initial-admin-secret:
    For password only:
        kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo
    For yaml output:
        kubectl -n argocd get secret argocd-initial-admin-secret -o yaml

# Configure ARGO CD