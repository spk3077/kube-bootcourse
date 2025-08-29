# Info
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
