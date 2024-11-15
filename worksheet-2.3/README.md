## 1. Aim/Overview of the practical: 
   To perform Kubernetes architecture, building blocks and container orchestration.
### 2. Objective of this experiment: 
	Exploring the key components of the Kubernetes architecture, such as the master node and worker nodes.

	Understanding the role of each component, such as the API server, controller manager, scheduler, and etcd.

	 Examining the communication and interaction between the master node and worker nodes.
### 3. Steps for experiment/practical:

Kubernetes (often abbreviated as K8s) is a powerful container orchestration platform that automates the deployment, scaling, and 
management of containerized applications. Understanding its architecture and key building blocks is essential for effectively using Kubernetes
in a cloud-native environment. Here's an overview of the architecture, building blocks, and the core concepts of Kubernetes.


#### Kubernetes Architecture:
 
![image](https://github.com/user-attachments/assets/ae4c50d8-14b9-4834-ac41-5719acccb39a)

Kubernetes architecture is built around a master-slave or client-server model, where the Master Node is responsible for managing the Kubernetes cluster, and Worker Nodes run the containerized applications.
### 1. Master Node
The master node is the control plane for the Kubernetes cluster. It manages the cluster's state and configuration. Key components include:

•	API Server (kube-apiserver): The central management entity that exposes the Kubernetes API. It handles REST operations and provides a frontend to the cluster’s shared state.

•	Controller Manager (kube-controller-manager): It runs controller processes that handle routine tasks. Each controller is responsible for a specific aspect of the cluster, such as replication and scaling.

•	Scheduler (kube-scheduler): It watches for newly created pods and assigns them to worker nodes based on resource availability and constraints.

•	etcd: A distributed key-value store that stores all cluster data, including configurations and states.

### 2. Worker Nodes
Worker nodes are responsible for running the containerized applications. Key components include:

•	Kubelet: An agent that runs on each worker node. It ensures that the containers are running in a pod and communicates with the API server.

•	Kube Proxy: Manages network communication to and from pods. It maintains network rules and handles service discovery.

•	Container Runtime: Software that is responsible for running the containers. Common container runtimes include Docker, containerd, and CRI-O.

### 3. Networking
Kubernetes uses a flat network model that allows pods to communicate with each other without NAT (Network Address Translation). Key concepts include:

•	Services: Abstracts access to a set of pods. Services provide a stable endpoint for clients to access the applications running in the pods.

•	Ingress: Manages external access to services, typically HTTP, and provides load balancing, SSL termination, and routing.

### Building Blocks of Kubernetes:
Kubernetes is built around several core concepts and building blocks:
1. Pod
The smallest deployable unit in Kubernetes, a pod is a group of one or more containers that share storage and network resources. Pods can run on any worker node and can scale horizontally.

2. ReplicaSet
Ensures that a specified number of pod replicas are running at any given time. If a pod fails, the ReplicaSet creates a new pod to maintain the desired state.

3. Deployment
A higher-level abstraction that manages ReplicaSets. Deployments provide declarative updates to applications, allowing users to roll out and roll back changes easily.

4. Namespace
A way to divide cluster resources between multiple users. Namespaces allow for a virtual cluster within a physical cluster.

5. ConfigMap and Secret
•	ConfigMap: Used to store non-sensitive configuration data as key-value pairs.

•	Secret: Similar to Config Map but designed to store sensitive information like passwords, tokens, or SSH keys.

6. Volume
A directory that is accessible to the containers in a pod, providing persistent storage. Kubernetes supports various volume types, including host Path, persistent Volume, and cloud provider-specific volumes.

### Container Orchestration:
Kubernetes provides robust orchestration features to manage the lifecycle of containers:

•	Scaling: Automatically scales applications based on load using Horizontal Pod Auto-scaler.

•	Load Balancing: Distributes traffic to pods based on user-defined criteria and health checks.

•	Self-healing: Automatically replaces or reschedules pods that fail, ensuring the desired state is maintained.

•	Rolling Updates: Allows updating applications without downtime, gradually replacing old versions with new ones.

•	Resource Management: Manages resource allocation to containers using requests and limits to ensure optimal utilization.

### Key benefits of using Kubernetes for container orchestration: 

•	Scalability: Easily scale applications up or down by adjusting the number of pods. 

•	High Availability: Automatically restart failing containers to maintain application uptime. 

•	Simplified Management: Manage complex container deployments through a single interface. 

•	Portability: Run applications across different cloud providers or on-premises infrastructure. 


### 8. Result/Output/Writing Summary:
#### The result of this experiment:
Kubernetes is a powerful container orchestration platform that simplifies deploying and managing containerized applications. 
By understanding its architecture, building blocks, and orchestration capabilities, you can effectively utilize Kubernetes to build scalable, resilient, 
and efficient applications in a cloud-native environment.
