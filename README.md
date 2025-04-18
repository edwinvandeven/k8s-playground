# k8s-playground

## Setup

### Minikube

Run minikube with the following commands, to ensure compatability with the prometheus operator
```
$ minikube delete && minikube start --container-runtime=containerd --kubernetes-version=v1.32.3 --memory=6g --bootstrapper=kubeadm --extra-config=kubelet.authentication-token-webhook=true --extra-config=kubelet.authorization-mode=Webhook --extra-config=scheduler.bind-address=0.0.0.0 --extra-config=controller-manager.bind-address=0.0.0.0
```

With a CPU & memory configuration
```
minikube start --cpus 8 --memory 16g --container-runtime=containerd --kubernetes-version=v1.32.3 --memory=6g --bootstrapper=kubeadm --extra-config=kubelet.authentication-token-webhook=true --extra-config=kubelet.authorization-mode=Webhook --extra-config=scheduler.bind-address=0.0.0.0 --extra-config=controller-manager.bind-address=0.0.0.0
```

Docs:
https://github.com/prometheus-operator/kube-prometheus