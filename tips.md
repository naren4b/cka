# How to check supported api-versions in a k8s cluster
```kubectl api-versions```

# How to configure private docker registry in your k8s cluster
```
kubectl create secret docker-registry regsecret \
    --docker-username=USERNAME \
    --docker-password='PASSWORD' \
    --docker-email=user@email.com
```
in the deployment file 

```
spec:
  imagePullSecrets:
    - name: regsecret
```

# How make the k8s to pull the latest image (```imagePullPolicy```  should set to ```always```)
```kubectl scale --replicas=0 deploy/my-app && kubectl scale --replicas=1 deploy/my-app```

# run a busy-box container 
```
kubectl run busybox --image=busybox --command sleep 1000 --dry-run=client -o yaml > busy.yaml
```

# cluster ip range 
Set at kube-api service configuration 

# how to check iptable rules 
iptables -L -t net | grep <service-name> 

# iptable entry

cat /var/log/kube-proxy.log

