

## Setup

Initailize cluster

`kubeadm init --token=102952.1a7dd4cc8d1f4cc5`{{execute HOST1}}

If you have stale setup you can run `kubeadm reset`{{execute HOST1}}

Token info 

`kubeadm token list`{{execute}}

Setting environment created by kubeadm

```
sudo cp /etc/kubernetes/admin.conf $HOME/
sudo chown $(id -u):$(id -g) $HOME/admin.conf
export KUBECONFIG=$HOME/admin.conf
```{{execute HOST1}}


Lets join our node

`kubeadm join --token=102952.1a7dd4cc8d1f4cc5 [[HOST_IP]]:6443`{{execute HOST2}}

Let check k8s pods

`kubectl get pod -n kube-system`{{execute HOST1}}

Check if node is connected to master


`kubectl get nodes`{{execute HOST1}}

This setup requires weave CNI 

`kubectl apply -f /opt/weave-kube`{{execute HOST1}}

Check component status

`kubectl get cs`{{execute HOST1}}
