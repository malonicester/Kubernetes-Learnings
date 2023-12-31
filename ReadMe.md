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
kubectl get object_name(service,pod,deployment etc) -l <label_name>=value
```

- Delte Pods using label
```
kubectl delete pod -l <label_name>=value
```


- Set based selector in Kubernetes
```
kubectl get pods 'label_name in (val_1,val_2)'
```


### Kubernetes Networking


- Accessing terminal of runnig container inside a pod
```
kubectl exec <pod_name> -c <container_name> -it -- /bin/bash
```

### Volumes in Kubernetes
- Emptydir
  - This type volumes is a empty directory present inside the pod and is shared among the containers running inside the pod.
  - for example - if two containers are runnig inside a pod and a emptydir is used as volume then both will write in the same directory.
  - As this is created outside the container it remains intact even if the container is destoryed.
  - But if the pod is destoryed it will be destoryed for ever.

- Persistent Volumes
  - In case of volume types like emptydir and hostpath it is destoryed when the pod is destoryed. So the newly created pod coming from replicaset won't have that files.
  - And an other case can be when a pod is destroyed it is not guranteed that the newly created pod can be created in any node inside the cluster.
  - So we can create the volume inside the cluster so that the newly created pod can have access to the old pod files and data.
  - Cloud Providers like AWS provide  EBS(Elastic Block Store) which can be divided 
  accessed by EC2 instance only.

### Config Map and Secrets
- Create a config map
```
kubectl create configmap <map_name> --from-file=<file_name>
```