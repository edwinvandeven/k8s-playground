# k8s-playground

## Setup

### Minikube

Run minikube with the following commands, to ensure compatability with the prometheus operator

```bash
$ minikube delete && minikube start --container-runtime=containerd --kubernetes-version=v1.32.3 --bootstrapper=kubeadm --extra-config=kubelet.authentication-token-webhook=true --extra-config=kubelet.authorization-mode=Webhook --extra-config=scheduler.bind-address=0.0.0.0 --extra-config=controller-manager.bind-address=0.0.0.0
```

With a CPU & memory configuration

```bash
minikube start --cpus 8 --memory 16g --container-runtime=containerd --kubernetes-version=v1.32.3 --bootstrapper=kubeadm --extra-config=kubelet.authentication-token-webhook=true --extra-config=kubelet.authorization-mode=Webhook --extra-config=scheduler.bind-address=0.0.0.0 --extra-config=controller-manager.bind-address=0.0.0.0
```

#### LoadBalancer type services

In a separate tab run the following command to assign load balancer IPs from minikube's range.

```bash
minikube tunnel
```

#### Docs
https://github.com/prometheus-operator/kube-prometheus

