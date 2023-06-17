## Kubernetes(K8s)
### Cli commands
- Create Deployment
```
kubectl create deployment <deployment_name> --image=<image_name>
```
- Edit Deployment
```
- kubectl edit deployment <deployment_name>

- kubectl delete deployment <deployment_name>

- kubectl delete pod <pod_name>

- kubectl describe deployment <deployment_name>

- kubectl describe pod <pod_name>

- kubectl logs <pod_name>

```
- Enter Terminal of a running container

```
- kubectl exec -it <pod_name> -- bin/bash
```
- Exit the terminal of a runnig container
```
- exit
```

---
- Apply the K8s Configuration yaml
```
- kubectl apply -f config.yaml
```
- Get Yaml Of Pod
```
kubectl get deployment -o yaml
``` 
- Get IP Address of Kubernetes Pods
```
kubectl get pod -o wide
```


### Labels
- Label a pod using command line
```
- kubectl label pod <pod_name>  <label_name>=value
```
```
- kubectl get pod <pod_name> --show-lables=true
- kubectl get pod/pods --show-labels=true
```

- Get Pods By Label
```
kubectl get pods -l <label_name>=value
```

- Delte Pods using label
```
kubectl delete pod -l <label_name>=value
```

