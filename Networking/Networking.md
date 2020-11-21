
# Switch 
1. Enables connectivity within a single network (home, small office ) for the connected device(s)

![Switch](img/switch.png)

# Router 
1. Connectes between two different network 
2. It has two unique ids in 2 different networks 

```
ip route 

```
# Gateway 

![Router](img/route.png)

# Networking related Commands
### Check the ip adress 
```
ip addr
```

### To see the network interface for the host 
```
ip link
````

### Give an IP Address 
```
ip addr add <CIDR> dev eth0
```


ip netns

ip netns add  <name>

ip netns exec <name> ip link



iptables rules 

```
iptables -nvL -t nat 


# How many nodes are part of this cluster?
```
Run the kubectl get nodes command
```
# What is the network interface configured for cluster connectivity on the master node?
node-to-node communication
```
Run the `ip link` command and identify the interface
```
or 
```
ifconfig -a 

```

or (in ubuntu)
```
cat /etc/network/interfaces
```


# What is the IP address assigned to the master node on this interface?
```
kubectl get nodes -o wide
```
or 

```
ifconfig <interface-name>

```

# What is the MAC address of the interface on the master node?
```
 ip link show <interface-id>

```
# What is the MAC address assigned to any node?
run following command from the current node 
```
arp <node-name>
```

# We use Docker as our container runtime. What is the interface/bridge created by Docker on this host?

Run the command `ip link` and look for a `bridge interface` created by docker

# If you were to ping google from the master node, which route does it take?
What is the IP address of the Default Gateway?
```
ip route show default
```
# What is the port the kube-scheduler is listening on in the master node?
```
Use the command netstat -nplt

```

# Notice that ETCD is listening on two ports. Which of these have more client connections established?
Correct! That's because 2379 is the port of ETCD to which all control plane components connect to. 2380 is only for etcd peer-to-peer connectivity. When you have multiple master nodes. In this case we don't.

```
netstat -anp | grep etcd
```

# Inspect the kubelet service and identify the network plugin configured for Kubernetes.
ps aux | grep kubelet | grep network

ps aux | grep kubelet | grep cni


# What is the Networking Solution used by this cluster?
```
Check the config file located at /etc/cni/net.d/

```






1. container <--> container (pod network)
(this is spcific to the CNI plugin that we use )
chekc the logs of CNI plugin 

2. container <---> Node
3. conatiner (node1)  <---> container (node2)
4. container(nodeX) <---> outside-cluster


cluster ip range 
kube-api server take care of it and allocated by the it's configuration 
static pod configuration 
what proxy is configured for the kube-proxy 

svc ip addr aka cluster-ip , kube-proxy uses iptable proxy (iptable rules DNAT)to send traffic to actual container 



# node-a <--> node-b

ip addr
ifconfig -a
k get nodes -o wide 


There are multiple entries in the dns sever 
- pod dns i.e <pod-ip>.<ns>.svc.cluster.local
- service dns <service-name>.<ns>.svc.cluster.local



















































```



