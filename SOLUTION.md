### What command do you run to see all the ArgoCD pods?

```
kubectl get pods -n argocd
```

### Define GitOps in your own words

> GitOps is a way of handling continuous delivery by automating the majority of the process. It works by monitoring commits/pushes to a git repository, and updating kubernetes anytime there is a change to the config files.

### Share a screenshot on your NGiNX application shown in ArgoCD, showing it synchronised

![NGINX app in ArgoCD](/nginx-app.png)

### Share a screenshot on your NGiNX application shown in ArgoCD, showing it "Out of Sync"

![NGINX app out of sync in ArgoCD](/nginx-out-of-sync.png)

### Screenshot of both the NGINX and the JAVA app running in ArgoCD

![Apps shown in ArgoCD](/apps.png)
