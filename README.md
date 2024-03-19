# Setup
## kubectl config
```
gcloud container clusters get-credentials <cluster_name> --region=<region>
```

## Install Argo CD
```
k apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

## Setup Root
```
k port-forward svc/argocd-server -n argocd 8080:443
```


## Setup SSO Client Secret
```
echo -n <secret> | base64
```
```
k -n argocd edit secret argocd-secret
```
```
# ...
type: Opaque
data:
  dex.github.clientSecret: <encoded_secret>

```


