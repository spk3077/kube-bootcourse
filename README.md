# kube-bootcourse
Boot.dev Kubernetes Course

# YAML Deployment
- Under spec: section the replicas field specifies the number of duplicate pods. Edit this number when you want duplicate pods
- status: section just contains metadata about the current status, changing it doesn't modify anything
    - is automatically updated by the control plane


apiVersion: apps/v1 - Specifies the version of the Kubernetes API you're using to create the object (e.g., apps/v1 for Deployments).
kind: Deployment - Specifies the type of object you're configuring
metadata - Metadata about the deployment, like when it was created, its name, and its ID
spec - The desired state of the deployment. Most impactful edits, like how many replicas you want, will be made here.
status - The current state of the deployment. You won't edit this directly, it's just for you to see what's going on with your deployment.