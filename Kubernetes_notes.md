
# Kubernetes Notes

## Architecture

### control plane
	- API server
	- etcd
	- scheduler
	- controller manager
	- cloud controller manager
### worker nodes 
	- kubelet
	- kube-proxy
	- container runtime

## Pod

  

### What is Pod ? 
Pod is wrapper around the container

### Ports

![Ports](image.png)

### how to debug a pod :

	kubectl describe pod <pod name> which gives the every details about the pod.
	
	kubectl logs <Name of the pod> -c <name of the container>

  
  

## Deployments:

- Deployment Workflow:

	- Deployment will create ReplicaSet

	- ReplicaSet [Kubernetes controller] to create the desired number of pods mentioned in the yaml manifest.

	- How kubernetes achieve autohealing and autoscaling :

- autohealing and autoscaling - you need to create deployment (Wrapper on top of your pod). Its a way to deploy application onto the pod.

  
 ## Service


 ## annotatins ** 
  

## Interview questions

- What is Difference between container , pod and deployment ?

	- Container workflow :

		- write DockerFile

		- create image m

		- push image to registry

		- create container

	- Pod :

		- write yaml file [more declarative way of defining the using YAML]

		- run time specification of the containers.

		- pod contain multiple containers - primary application , service mesh , side car contariner (dependent container)etc.

	- deployment :

		- autohealing capabilities.

		- autoscaling capabilities.

- what is Difference between deployment and replicaset ?

	- Replicaset is basically kubernets controller is responsible for maintaining the desired state. It is responsible for implementing/ providing autohealing capability.
    - A ReplicaSet's purpose is to maintain a stable set of replica Pods running at any given time. As such, it is often used to guarantee the availability of a specified number of identical Pod

	- Deployment is the configuration written in the manifest.

	- how to do list all the resources in the namespaces?
		kubectl get all
	
- what are the different types of services in kubernetes ?
	- NodePort:
	- ClusterIP:
	- LoadBalancer:
- what is the difference between NodePort and LoadBalancer type service ?
- what is the role of kubelet?
- Day to Day activities on Kubernetes?
	- We manage kubernetes clusters within the organization
	- Troubleshooting the issues reported by developers.
	- Maintainance on the nodes
	- We serve as SMEs for kubernetes.