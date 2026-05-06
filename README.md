# Infrastructure Repo

## Layout
- `k8s/base`: shared manifests
- `k8s/staging`: staging overlay
- `k8s/production`: production overlay
- `argocd/applications.yaml`: Argo CD apps with auto-sync

## Deploy
1. Install ingress controller in cluster.
2. Install Argo CD.
3. Apply Argo CD apps:
   - `kubectl apply -f argocd/applications.yaml`
4. Argo CD syncs from this repo automatically.

## Required Update
- Replace image names (`yourdockerhub/*`) with actual registry names.
- Replace `repoURL` in Argo CD application manifest.
- Replace ingress host from `aitask.local` to your domain.
