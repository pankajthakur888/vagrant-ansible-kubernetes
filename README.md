# vagrant-ansible-kubernetes
Combination of Vagrant and Ansible to spin up a Kubernetes cluster

### Prerequisites
- Vagrant
- Ansible

### Define amount of nodes
in Vagrantfile:
```
N = 2
```


### Spin up cluster
```
$ vagrant up
```

### Configure Network bridged wifi or lan
Note My local network on wifi pool ip 192.168.1.0/24
allow from firewall if use 
k8-master 192.168.1.101
node-1 192.168.1.102
node-2 192.168.1.103
```
$ ==> k8s-master: Available bridged network interfaces:
1) wlp0s20f3
2) enp0s31f6

$ ==> node-1: Available bridged network interfaces:
1) wlp0s20f3
2) enp0s31f6

$ ==> node-2: Available bridged network interfaces:
1) wlp0s20f3
2) enp0s31f6

```


### Verify on master
```
$ vagrant ssh k8s-master
$ kubectl get nodes
NAME         STATUS   ROLES                  AGE     VERSION
k8s-master   Ready    control-plane,master   5m6s    v1.23.0
node-1       Ready    <none>                 2m59s   v1.23.0
node-2       Ready    <none>                 68s     v1.23.0
```
vagrant provision
