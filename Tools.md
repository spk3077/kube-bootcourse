# Kubernete Tools

## Minikube
For single-node Kubernetes clusters on a single machine. Minikube is typically not used in production because in production you generally have multiple nodes (machines) that form a cluster of servers supporting a service.

REMEMBER THIS IS NOT ALWAYS TRUE AND SEVERAL PRODUCTS HAVE KUBERNETES JUST RUNNING LOCALLY ON ONE BOX

#### kind
kind create cluster --name test-cluster
 Kind uses Docker containers to simulate Kubernetes nodes.

#### k3d
k3d cluster create my-cluster
k3d is a lightweight tool that lets you run K3s (a minimal Kubernetes distribution) inside Docker containers. It’s essentially a wrapper around K3s, designed to make it super easy to create and manage Kubernetes clusters locally—especially for development and testing.

#### MicroK8s (Ubuntu)
sudo snap install microk8s --classic
MicroK8s is a lightweight, production-grade Kubernetes distribution developed by Canonical (the makers of Ubuntu). It’s designed to run on single-node setups but can also scale to multi-node clusters with high availability. Its main appeal is simplicity, speed, and low resource usage—making it ideal for local development, CI/CD, edge computing, and IoT.

#### Docker Desktop
##### Enable Kubernetes in Docker Desktop settings

#### k0s (Linux)
curl -sSLf https://get.k0s.sh | sudo sh
sudo k0s install controller
sudo systemctl start k0scontroller
k0s (pronounced "kay-zero-ess") is a lightweight, open-source, and CNCF-certified Kubernetes distribution designed for simplicity, flexibility, and zero friction in deployment. It’s ideal for developers, edge computing, IoT, and enterprises looking for a minimal yet powerful Kubernetes setup.

#### Kubeadm (Linux)
sudo kubeadm init
Kubeadm is a tool provided by the Kubernetes project to help you bootstrap a production-grade Kubernetes cluster.