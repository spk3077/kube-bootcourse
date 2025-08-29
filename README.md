# kube-bootcourse
Boot.dev Kubernetes Course

## Minikube
For single-node Kubernetes clusters on a single machine. Minikube is typically not used in production because in production you generally have multiple nodes (machines) that form a cluster of servers supporting a service.

REMEMBER THIS IS NOT ALWAYS TRUE AND SEVERAL PRODUCTS HAVE KUBERNETES JUST RUNNING LOCALLY ON ONE BOX

### Alternatives to Minikube that are often used in production
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


# Great Information
By default, resources inside of Kubernetes run on a private, isolated network. They're visible to other resources within the cluster, but not to the outside world.

A Pod is the smallest deployable unit in Kubernetes. It can contain one or more containers that share:
- Storage volumes
- Network namespace
- IP address

A Deployment is a higher-level abstraction that manages Pods via ReplicaSets. It ensures that the desired number of pod replicas are running and handles updates and rollbacks.
🔹 Key Characteristics of Deployments:
- Automatically replaces failed pods
- Supports rolling updates and rollbacks
- Scales easily by changing the replicas field
- Created with kubectl apply -f deployment.yaml

AKA: Pods: Run one or more containers, Deployments: Manage lifecycle of Pods

To zoom way out, Kubernetes' job is to run software applications, and applications require resources. Resources are things like:
    CPU
    Memory
    Disk space

Kubernetes' job is to manage those resources and allocate them to the applications that are running on it.

Kubernetes manages the resources that applications require and automatically distributes the load across nodes


# Commands

```
# Necessary for starting minikube cluster and default namespace. The extra config can be left only, only added for project API interactions with boot.dev
minikube start --extra-config "apiserver.cors-allowed-origins=["http://boot.dev"]"

# Opens a browser window with locally hosted dashboard for your cluster
minikube dashboard --port=63840

# Everytime you restart and want to re-enable your minikube cluster. You ought to create a profile that saves any custom intial configurations
minikube start -p bootdev --extra-config "apiserver.cors-allowed-origins=[\"http://boot.dev\"]"
# Now start with the bootdev profile
minikube start -p bootdev

# To stop and Restart 
minikube stop
minikube delete

# Creates a 'deployment' using a docker image hosted on dockerhub with the name synergychat-web
kubectl create deployment synergychat-web --image=docker.io/bootdotdev/synergychat-web:latest

# Retrieves all deployment names and their status
kubectl get deployments

# Retrieve pod names and their status
kubectl get pods

# Port forward a pod's service to the outside
kubectl port-forward PODNAME 8080:8080

# To edit deployment
kubectl edit deployment DEPLOYMENT-NAME

# Print logs of a pod
kubectl logs PODNAME

# Kill a pod
## This automatically just restarts a particular pod

kubectl delete pod PODNAME

```


# YAML Deployment
- Under spec section the replicas field specifies the number of duplicate pods. Edit this number when you want duplicate pods

