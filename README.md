# Plan for appearing CKA

https://github.com/cncf/curriculum/blob/master/CKA_Curriculum_v1.28.pdf

### Cluster Architecture, Installation & Configuration

    - Check the master node component staus
    - Practice troubleshooting networking issues.
    - Create a Static Pod and Service
    - How many master nodes are available?
        2. How many worker nodes are available?
        3. What is the Pod CIDR of cluster1-worker1?
        4. What is the Service CIDR?
        5. Which Networking (or CNI Plugin) is configured and where is its config file?
        6. Which suffix will static pods have that run on cluster1-worker1?
        7. Change kubeconfig/context
    - Update Kubernetes Version and join cluster
    - Kubelet client/server cert info
    - Check how long certificates are valid[https://jvns.ca/blog/2017/08/05/how-kubernetes-certificates-work/]
    - Etcd Snapshot Save and Restore

### Security

- Understand Kubernetes security mechanisms, including Role-Based Access Control (RBAC).
- Practice creating roles, role bindings, and service accounts.
- Secret mounting

### Workloads & Scheduling

- Understand StatefulSets and DaemonSets, and practice creating and managing(Scheduling/ Resource limit/labeling/Readiness/liveness) them.
- Study Kubernetes concepts such as Pods, Deployments, Services, ConfigMaps, and Secrets.
- Scaling up and down
- Node and pod resource usage
- Manual Scheduling
- Multi Containers and Pod shared Volume

### Services & Networking

    - Learn about Kubernetes networking concepts, services, and Ingress.
    - Practice troubleshooting networking issues.
    - NetworkPolicy

### Storage

- Study how to manage storage in Kubernetes using Persistent Volumes (PVs) and Storage Classes.
- Practice setting up and using different storage options.

### Troubleshooting

- Practice identifying and resolving common issues in a Kubernetes cluster.
- Explore kubectl debug and other troubleshooting tools.
- Imperative commands by Kubectl
- Cluster Event Logging
- POD and container logs
- System service status and logs[systemctl , journalctl]
- Curl Manually Contact API
- Change kube-apiserver parameters

##### extra links:

https://github.com/techiescamp/vagrant-kubeadm-kubernetes
https://devopscube.com/setup-kubernetes-cluster-kubeadm/
https://devopscube.com/cka-exam-study-guide/

https://alexander.holbreich.org/kubernetes-on-ubuntu/

https://www.redhat.com/en/blog/kubernetes-deep-dive-api-server-part-1
https://www.redhat.com/en/blog/kubernetes-deep-dive-api-server-part-2

Good Tips on small things :
https://akomljen.com/tag/kube-tips/

Setting up the test cluster Through KIND
https://hackmd.io/@mauilion/cka-lab
