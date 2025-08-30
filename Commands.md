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

# Wide output which includes IP addresses
kubectl get pods -o wide

# You can set up a webserver to view status of pods in your browser
kubectl proxy
# http://127.0.0.1:8001/api/v1/namespaces/default/pods

# Look at the YAML file for our current deployment
kubectl get deployment synergychat-web -o yaml > my-deployment.yaml

# Edit the YAML then apply it 
kubectl apply -f web-deployment.yaml

# Viewing replicasets
kubectl get replicasets


```