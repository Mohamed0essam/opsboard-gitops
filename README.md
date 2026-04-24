# opsboard-gitops

GitOps repository for OpsBoard Kubernetes deployment state.

## Purpose

This repo stores only deployment manifests (no application source code).
Argo CD should watch this repo and sync the target environment(s).

## Structure

- `k8s/base`: shared base manifests
- `k8s/staging`: staging overlay (kustomize)
- `argocd/applications`: Argo CD `Application` manifests

## Staging Deploy

```bash
kubectl apply -k k8s/staging
```

## Notes

- Keep real credentials out of Git.
- Create pull secrets (for private registries) directly in the cluster or via a secure secret workflow.
