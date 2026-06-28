# ci-cd

## Source control system
Deploy a source control system like Forgejo.
Have enabled both `http` and `ssh`. If `https` is required, we can use a `nginx` container with self signed certs.


## CD system
Deploy a CD system like ArgoCD in k8s


## Create a repo
Create a repo in forgejo and create a sample deployment file for an application.
```
mkdir -p deploy
touch deploy/deployment.yaml
```
Copy the contents of [deployment.yaml](./test-app/deploy/deployment.yaml) and add it to the `deploy/deployment.yaml` file in your repo.

Commit and push the changes to repo


## Configure ArgoCD
In ArgoCD, configure the repository
```
Settings > Repositories > Connect Repo
```

Once the repo is configured, create an application and set `Sync Policy` to automatic.
Whenever there is a change in the repo, ArgoCD will automatically sync the changes to the cluster.