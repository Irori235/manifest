# Setup
## kubectl config
```
gcloud container clusters get-credentials <cluster_name> --region=<region>
```

## Install Argo CD
```
k apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```
