## 1.Aim/Overview of the practical: 
Install Kubernetes/ minikube and kubetools and Deploy first container in Kubernetes.
### 2.Objective of this experiment: 
The objective of this experiment is to understand the core components and workflow of deploying a containerized application using Kubernetes in a local development environment. By setting up Kubernetes (with Minikube) and deploying a simple application, you'll gain hands-on experience with container orchestration, resource management, and Kubernetes tooling (kubectl).
### 3. Steps for experiment/practical:

1)Before starting the minikube installation, it is recommended to install all available updates on your system. Run following command.
$ sudo apt update
$ sudo apt upgrade -y

2) Download and Install Minikube Binary
To download and install minikube binary, run following commands,
$ curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
$ sudo install minikube-linux-amd64 /usr/local/bin/minikube
$ minikube version

![image](https://github.com/user-attachments/assets/3aeb27f7-c13c-4fa2-8e90-97b5a97f42f6)

 


3) Install Kubectl tool

Kubectl is a command line tool, used to interact with your Kubernetes cluster. So, to install kubectl run beneath curl command.

$ curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl
Next, set the executable permission on it and move to /usr/local/bin

$ chmod +x kubectl

$ sudo mv kubectl /usr/local/bin/
Verify the kubectl version, run

$  kubectl version -o yaml
![image](https://github.com/user-attachments/assets/1938875b-e703-43b5-a1b0-32dc169cc83c)

 

4) Start Minikube Cluster
Now that Minikube is installed, start a Kubernetes cluster using the following command:
$ minikube start --driver=docker
![image](https://github.com/user-attachments/assets/380ed36e-6bdd-4af1-b714-cab2132e6a29)
 

This command initializes a single-node Kubernetes cluster, and it might take a few minutes to download the necessary components.
Once the minikube has started, verify the status of your cluster, run
$ minikube status
![image](https://github.com/user-attachments/assets/fb841ab5-fcbd-4e17-9706-36c9cd9f70c1)
 

5) Interact with Your Minikube Cluster

Use kubectl to interact with your Minikube Kubernetes cluster. For example, you can check the nodes in your cluster:
$ kubectl get nodes

![image](https://github.com/user-attachments/assets/e2f395bd-e9b7-449b-b150-f9208fafb76a)


 
Try to deploy a sample nginx deployment, run following set of commands.
$ kubectl create deployment nginx-web --image=nginx
$ kubectl expose deployment nginx-web --type NodePort --port=80
$ kubectl get deployment,pod,svc
![image](https://github.com/user-attachments/assets/a07d93a9-c6c1-49df-b4b6-333473aeceee)
 

6) Managing Minikube Addons
If you want to add some additional functionality toy Kubernetes cluster like Kubernetes dashboard, ingress controller and more. You can enable these with addons. To view all the available addons, run
$ minikube addons list
![image](https://github.com/user-attachments/assets/b8b7212e-e5ac-4c20-8c86-f5f6656694bb)
 

In order to enable addons, run
$ minikube addons enable dashboard
$ minikube addons enable ingress
To start the Kubernetes dashboard run below command, it will automatically launch the dashboard in the web browser as shown below:
$ minikube dashboard
 
![image](https://github.com/user-attachments/assets/dafbf8f7-4960-489c-aaa3-c2eaf5ea10d7)

![image](https://github.com/user-attachments/assets/758320a6-5bb3-44f5-9602-f566c965c7d4)
 



7) Managing Minikube Cluster

To stop and start the minikube cluster, run beneath commands.
$ minikube stop
$ minikube start
In order to delete the minikube cluster, run
$ minikube delete
 
![image](https://github.com/user-attachments/assets/d9437c5b-ed37-4808-9ac9-9dfcf61c55cc)


### 8. Result/Output/Writing Summary:
#### The result of this experiment:
Upon completion, you should have:

•	A fully functional local Kubernetes cluster with Minikube.

•	A deployed NGINX application accessible through the Service URL provided by Minikube.

•	Verified application status and logs that confirm the container is operating as expected.

This output demonstrates that you have successfully created and exposed a containerized application in a Kubernetes environment.
