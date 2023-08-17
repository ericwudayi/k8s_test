# k8s_test

I cannot retreive all the pods with one yaml because of permission issue.
Hence, I divide the steps into two, first create the ServiceAccount and Role, and then I create the pod with account with permission to read the default namespace

```
## create the  role
kubectl apply -f service-account.yaml
kubectl apply -f pod-list-role.yaml
kubectl apply -f pod-list-rolebinding.yaml
## run pod
kubectl apply -f curl-pod.yaml
## see the log
kubectl logs simple-curler
```