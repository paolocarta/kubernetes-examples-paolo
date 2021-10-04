
# Argo CD

`TODO` add SYNC-WAVE

Current version: `2.0.3`

Customizations:

  - 3_configurations/
    - argocd-cm.yaml
    - argocd-rbac-cm.yaml
  - 3_secrets/
    - gitlab-creds.yaml

## Roadmap

### Features

- [ ] `TBD` argo-app for self management using sync-wave
- [ ] prometheus monitoring
- [ ] `TBD` use ApplicationSet
- [ ] `TBD` use `connaisseur` to deploy only signed container images
- [ ] `TBD` SSO with GCP

### Security

- [ ] https vs ssh access to git repos

---

## Instructions

```bash
kustomize build . | kubectl apply -f -
kubectl apply -f app.yaml
```

---

## Cluster investigation commands

### gcloud

gcloud config config-helper --format=json

### argo-util

argocd-util cluster generate-spec <KUBECONFIG_CTX> > <KUBECONFIG_CTX>.yaml

### argocd

kubectl port-forward svc/argocd-server -n argocd 8443:443

argocd login localhost:8443

argocd cluster add <KUBECONFIG_CTX>

---

## Links

### Declarative setup

See [official doc](https://argo-cd.readthedocs.io/en/stable/operator-manual/declarative-setup/)

### Users

#### Local

See [official doc](https://argo-cd.readthedocs.io/en/stable/operator-manual/user-management/)

#### Google integration

See [official doc](https://argo-cd.readthedocs.io/en/stable/operator-manual/user-management/google/)

#### RBAC

See [official doc](https://argo-cd.readthedocs.io/en/stable/operator-manual/rbac/)

### Monitoring

See [official doc](https://argo-cd.readthedocs.io/en/stable/operator-manual/metrics/)

### Ingress

See [official doc](https://argo-cd.readthedocs.io/en/stable/operator-manual/ingress/)

### Notifications

See [official doc](https://argo-cd.readthedocs.io/en/stable/operator-manual/notifications/)

### High availability

See [official doc](https://argo-cd.readthedocs.io/en/stable/operator-manual/high_availability/)

### Security

See [official doc](https://argo-cd.readthedocs.io/en/stable/operator-manual/security)

#### External cluster credentials

See [official doc](https://argo-cd.readthedocs.io/en/stable/operator-manual/security/#external-cluster-credentials)

To rotate baerer token and revoke Argo CD's access to a managed cluster, see [official doc](https://argo-cd.readthedocs.io/en/stable/operator-manual/security/#external-cluster-credentials)
