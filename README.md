# Kubernetes - Quick Command Reference

Here's a run down of all (ok, most of) of the commands used in the Kubernetes Microservices

## Minikube

#### minikube start

starts minikube. If this hangs (wait 15 minutes), then see the video in section 3 that addresses common problems

#### minikube stop

stops the minikube virtual machine. This may be necessary to do if you have an error when starting

#### minikube delete

do this to completely wipe away the minikube image. Useful if minikube is refusing to start and all else fails. Also you can delete all files in <home>/.minikube and <home>/.kube

#### minikube env

find out the required environment variables to connect to the docker daemon running in minikube.

#### minikube ip

find out the ip address of minikube. Needed for browser access.

## Kubectl

#### kubectl get all

list all objects that you’ve created. Pods at first, later, ReplicaSets, Deployments and

## Services

#### kubectl apply –f <yaml file>

either creates or updates resources depending on the contents of the yaml file

#### kubectl apply –f .

apply all yaml files found in the current directory

## Kubernetes -

#### kubectl describe pod <name of pod>

gives full information about the specified pod

#### kubectl exec –it <pod name> <command>

execute the specified command in the pod’s container. Doesn’t work well in Cygwin.

#### kubectl get (pod | po | service | svc | rs | replicaset | deployment | deploy)

get all pods or services. Later in the course, replicasets and deployments.

#### kubectl get po --show-labels

get all pods and their labels

#### kubectl get po --show-labels -l {name}={value}

get all pods matching the specified name:value pair

#### kubectl delete po <pod name>

delete the named pod. Can also delete svc, rs, deploy

#### kubectl delete po --all

delete all pods (also svc, rs, deploy)

## Deployment Management

#### kubectl rollout status deploy <name of deployment>

get the status of the named deployment

#### kubectl rollout history deploy <name of deployment>

get the previous versions of the deployment

#### kubectl rollout undo deploy <name of deployment>

go back one version in the deployment. Also optionally -- to-revision=<revision number>
