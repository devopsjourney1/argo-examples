

# Follow this video to be a ArgoCD Boss
https://youtu.be/JLrR9RV9AFA


# Installing latest/stable version of ArgoCD
```
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

### Forward Ports
```
k get services -n argocd
kubectl port-forward service/argocd-server -n argocd 8080:443
```

### Get Credentials
```
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d
```

# Install ArgoCD CLI / Login via CLI
```
brew install argocd
kubectl port-forward svc/argocd-server -n argocd 8080:443
argocd login 127.0.0.1:8080
```

# Creating an Application using ArgoCD CLI:
```
argocd app create webapp-kustom-prod \
--repo https://github.com/devopsjourney1/argo-examples.git \
--path kustom-webapp/overlays/prod --dest-server https://kubernetes.default.svc \
--dest-namespace prod
```

# Command Cheat sheet
```
argocd app create #Create a new Argo CD application.
argocd app list #List all applications in Argo CD.
argocd app logs <appname> #Get the application’s log output.
argocd app get <appname> #Get information about an Argo CD application.
argocd app diff <appname> #Compare the application’s configuration to its source repository.
argocd app sync <appname> #Synchronize the application with its source repository.
argocd app history <appname> #Get information about an Argo CD application.
argocd app rollback <appname> #Rollback to a previous version
argocd app set <appname> #Set the application’s configuration.
argocd app delete <appname> #Delete an Argo CD application.
```





