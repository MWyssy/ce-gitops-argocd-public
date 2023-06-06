# ArgoCD

## Introduction

It's time to go all GitOps and utilise [ArgoCD](https://argo-cd.readthedocs.io/en/stable/) to implement a GitOps workflow.

In this exercise you will deploy ArgoCD to your Kubernetes cluster so you'll have ArgoCD running in your cluster. 

Once deployed you will configure ArgoCD to monitor a repository (this one) and decide whether to make changes to your cluster.

## Instructions

### Starting kubernetes

You'll use local kubernetes for this one. 

Start up your local version of kubernetes and make sure you can connect to it using `kubectl`

You can test your `kubectl` connection but trying `kubectl get nodes`

**💡 HINT:** If you have recently used kubectl to connect to another Kubernetes cluster, you can switch the context back to **docker-desktop** by clicking the Docker Desktop icon, hovering over Kubernetes and choosing the **docker-desktop** context. Example shown in the screenshot

![Context menu showing Kubernetes context picker](./media/images/docker-desktop-kubernetes.png "Context menu showing Kubernetes context picker")

### Installing ArgoCD

Next you will deploy ArgoCD to your cluster.

To do this firstly create a separate [Kubernetes namespace](https://kubernetes.io/docs/concepts/overview/working-with-objects/namespaces/) for ArgoCD

```
kubectl create namespace argocd
```

Then apply the YML files associated with Argo. The command below just applies a YAML file called **install.yaml** that contains all the various services, deployments for ArgoCD.

```
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

You can see if your ArgoCD pods deployed by running:

```
kubectl get pods -n argocd
```

And you should see something similar to:

```
NAME                                                READY   STATUS    RESTARTS   AGE
argocd-application-controller-0                     1/1     Running   0          78s
argocd-applicationset-controller-55c8466cdf-srbt7   1/1     Running   0          78s
argocd-dex-server-6cd4c7498f-9v8z4                  1/1     Running   0          78s
argocd-notifications-controller-65cddcf9d6-kq574    1/1     Running   0          78s
argocd-redis-74d77964b-x8bh6                        1/1     Running   0          78s
argocd-repo-server-96b577c5-8b6b8                   1/1     Running   0          78s
argocd-server-7c7b5568cc-b85v8                      1/1     Running   0          78s
```

## Extension exercise

### Your own image and rolling out a change

You'll see there is a folder called **my-app** and the YAML files in there are empty.

Try populating those files in order to deploy one of your own containers to your cluster via ArgoCD.

To help guide you, you will need:

* Make sure you have pushed your image to your own container registry. You could do this with CircleCI if you have completed that task

* Make sure ArgoCD port forwarding is enabled, log in to ArgoCD and set up a new project

* Point that project at the **my-app** directory

## Submission process

1. Fork this repository

2. Remember to commit and push regularly to your repository

3. Complete the SOLUTION.md

4. Share link to your repository as indicated

## Further reading

[ArgoCD documentation](https://argo-cd.readthedocs.io/en/stable/)
