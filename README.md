# Argo CD OrbStack CI/CD Demo

This repository is a small GitOps practice project.

Flow:

1. Change `app/index.html`.
2. GitHub Actions builds and pushes a container image to GHCR.
3. GitHub Actions updates `k8s/deployment.yaml` with the new image tag.
4. Argo CD detects the Git diff as `OutOfSync`.
5. Manual sync deploys the new version to local OrbStack Kubernetes.

Deploy target:

- Cluster: local OrbStack Kubernetes
- Namespace: `demo`
- Argo CD application: `argocd-orbstack-cicd-demo`
