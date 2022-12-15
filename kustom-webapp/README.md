# Installation
```
kubectl version
```
*If you have 1.21 or above of kubectl you will have access to kubectl kustomize which is the recommended method. If you aren't on version 1.21 or above, upgrade kubectl.
*You could also download/use the 'kutomize' binary seperatly but the cmds are different.


# Viewing Kustomize Configs - (Using kubectl kustomize integration)
```
kubectl kustomize .
kubectl kustomize overlays/dev/
kubectl kustomize overlays/prod/
```

# Applying Kustomize Configs - (Using kubectl kustomize integration)
```
kubectl apply -k .
kubectl apply -k overlays/dev/
kubectl apply -k overlays/prod/
```
Note: if you get field is immutable error, check your configuration and try deleting the resources.


# Creating Namespaces if you dont have them already
```
kubectl create namespace dev; kubectl create namespace prod;
```


# Accessing the application
```
minikube service kustom-mywebapp-v1
minikube service kustom-mywebapp-v1 -n dev
minikube service kustom-mywebapp-v1 -n prod
```

# References:
https://github.com/kubernetes-sigs/kustomize/blob/master/README.md
https://kubectl.docs.kubernetes.io/guides/config_management/offtheshelf/
