
# Argo CD - Default projects

## Description

### Default

It represents the project to which ArgoCD associates all Applications without a project specified in the yaml.

### In-Cluster

It represents the project in which ArgoCD runs currently.

## Instructions

```bash
kustomize build . | kubectl apply -f -
```
