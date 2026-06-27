To deploy Argo CD in k8s, run the following command
```bash
kubectl create namespace argocd
kubectl apply -n argocd --server-side --force-conflicts -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```


Once deployed, run the following command to get the initial admin password:
```bash
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo
```

Login into the Argo CD UI using username `admin` and the password obtained from the previous command.
ArgoCD UI : https://[IP_ADDRESS]/