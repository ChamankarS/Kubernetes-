# Kubernetes command

## show cluster related info 
```
kubectl cluster-info
```

## show all nodes 
```
kubectl get nodes
```

### create pod 


kubectl run <pod_name> --image=<imagename>

```
kubectl run my-first-pod --image=nginx 
```
### pod related info 

```
kubectl get pods
```
```
kubectl get -o wide pods  #details
```
```
kubectl get -o wide nodes 
```
```
kubectl explain rc  #detail info about particular object
```
```
kubectl describe pod my-first-pod
```
```
 kubectl run my-pod --port=80 --image=nginx
```
```
 kubectl run my-pod --port=80 --image=nginx
```
  ## kubernetes Object 

   1.Pods -smallest deployment unit of the k8s 
   2.Nodes-worker nodes
   3.service-Expose application outside the cluster/conatiner
      * ClusterIP -> interal communication inside the cluster
      * Nodeport -> expose app outside the cluster
      * Loadbalancer -> expose app outside the cluster
   4. Namespace
   5. Replicaset
  

   6. Deployement
   7. DaemonSet
   8. statefulset
   9. ConfigMap
   10. Secrets
   11. Pv and Pvc
   12. RBAC
   13. Ingress Gateway

 ## Saveral way to scale the pod
   1. Update the yaml file
   2. Apply changes on the live object
```
 kubectl edit <pod-name>      #shift+A
```
   3. Update using scale command
   ```
 kubectl scale --replicas=5 <pod_name>
```
   4. Update the image in live deployment object not in yaml file
```
kubectl set image <deployment_name> \
image=nginx:1.9.1
```
5. Check rollout history
```
kubectl rollout history <deployment_name>
```
6. Rollback to previous version
```
kubectl rollout undo <deployment_name>
```
7. Create deployment through command and move into new file.
```
kubectl create deploy <deploy_name> --image=nginx --dry-run=client
```

---
## Manifest 

- configuration file of the object
