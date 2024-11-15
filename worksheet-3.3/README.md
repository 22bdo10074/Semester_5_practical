## 1.Aim/Overview of the practical: 
   Deploy multiple pod and multiple communication between pod and Kubernetes.
### 2.Objective of this experiment: 
•	To understand the concept of immutability in Kubernetes by deploying a simple application and updating it with new changes using immutable principles.

•	To understand the deployment of pod and communication between pod and Kubernetes.

### 3. Steps for experiment/practical:
 1.Communication Between Pods in Kubernetes

a)	Create Pod YAML Files
Define two pod YAML files, pod-a.yaml and pod-b.yaml: 
 
![image](https://github.com/user-attachments/assets/2c4c2361-142f-4100-aa44-571f2aab6953)
![image](https://github.com/user-attachments/assets/a94377eb-fac2-4ff7-8187-088ac79e152b)
![image](https://github.com/user-attachments/assets/53a43c9f-1392-46fd-9e8c-0822ac31046a)


 
 
b)	Apply the Pod YAML Files
         kubectl apply -f pod-a.yaml
         kubectl apply -f pod-b.yaml
![image](https://github.com/user-attachments/assets/19c22414-462e-4087-9489-b20931457da4)
          
c)	Verify Pods are Running
 kubectl get pods
![image](https://github.com/user-attachments/assets/031038a0-182d-4159-b98c-468cb126df94)
 
d)	Create Service YAML Files
Define services for each pod to enable communication.
![image](https://github.com/user-attachments/assets/d6c5e622-b874-460e-8e67-db2dd1333683)
![image](https://github.com/user-attachments/assets/0f04737c-86ae-4294-876f-9668f455d04c)

 
 
e)	Apply the Service YAML Files
 kubectl apply -f service-a.yaml
         kubectl apply -f service-b.yaml
![image](https://github.com/user-attachments/assets/6c69ef69-f5af-44c5-809f-a09bffbd9870)
     
f)	Verify Communication
Retrieve Cluster IPs and test inter-pod communication.
         kubectl get svc service-a
         kubectl get svc service-b
     
![image](https://github.com/user-attachments/assets/6a4926af-efda-4b02-8bcd-ac2a5bc0912e)

     

### Part 2: Demonstrating Immutability Concept in Kubernetes

1.	Deploy Initial Application
Define an initial application deployment in app-deployment.yaml:
 ![image](https://github.com/user-attachments/assets/c57e8eda-07a3-4ea0-a24c-2abe243dcaae)

2.   Update the Application Image
 Update the image version in app-deployment.yaml to nginx:1.21.1 and re- apply:
         kubectl apply -f app-deployment.yaml
         kubectl get pods
![image](https://github.com/user-attachments/assets/9eec33ed-c58f-4669-9003-b20933655d50)
      


3.	Verify Immutability Principle
Check the deployment details to see if a rolling update was used:
         kubectl describe deployment my-app

![image](https://github.com/user-attachments/assets/ee6ea457-9020-4c8d-ba30-37a58fe2f5c1)
 


### 4. Result/Output/Writing Summary:
The result of this experiment:
These steps demonstrate how to enable pod-to-pod communication in Kubernetes and how Kubernetes manages application updates in an immutable way using rolling updates, ensuring no downtime and easy rollback capability.
