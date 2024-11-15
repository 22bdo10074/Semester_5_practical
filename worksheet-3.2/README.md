## 1.Aim/Overview of the practical: 
Deploying a Node.js Application on Kubernetes with IBM Containers.
### 2.Objective of this experiment: 
a)	Creating a Node.js Application

b)	Creating a Dockerfile

c)	Building an Image and Pushing it to Docker Hub

d)	Creating Kubernetes Deployment and Services

e)	Deploying the application in a local Cluster
### 3. Steps for experiment/practical:
   
Creating the Node.js Application:

•	Initialize a Node.js project using npm init.

•	Develop an index.js file that uses Express to handle various routes, responding with JSON messages. 


![image](https://github.com/user-attachments/assets/bff6aa07-0563-4a98-8bba-43a4835a4bf4)


![image](https://github.com/user-attachments/assets/d579b5a4-16ae-4c31-be9c-e4ca9114ae50)

 
 
Creating a Dockerfile:
•	Build a Dockerfile to containerize the application, specifying the base image, working directory, dependencies, and the command to run the application.
![image](https://github.com/user-attachments/assets/4b37ce68-be4c-495e-b7af-6b9509059fff)

![image](https://github.com/user-attachments/assets/97511cc7-bb3c-4a5b-819c-d6ec54e39e1d)
 
 
Building and Verifying the Docker Image:
•	Build the Docker image using the command docker build -t <your_dockerhub_username>/node-app ..

•	Verify the image is created successfully by listing Docker images with docker images.
 
![image](https://github.com/user-attachments/assets/d1436572-c1b6-4fc0-a4c0-2ce3c319090f)
![image](https://github.com/user-attachments/assets/68cf8f98-15d8-4ee4-99c7-5417d8964f7d)
 

 Running the Docker Container:
•	Create and run a container from the Docker image using docker run -d -p 3000:3000 <your_dockerhub_username>/node-app.

•	Test the application by accessing it through a web browser at localhost:3000.
 
![image](https://github.com/user-attachments/assets/857003f9-53d2-423b-9f61-92325846556d)
![image](https://github.com/user-attachments/assets/dee5ac5a-0fa3-4a0e-bc9d-08a48e7e34c7)
![image](https://github.com/user-attachments/assets/7f6c1d60-74e2-4db5-bffd-16981b996e83)
![image](https://github.com/user-attachments/assets/05f4605d-bc78-4f7c-aaf9-4c3c6a576170)
 
 

 

Stopping and Removing the Container:
•	Use docker ps to find the running container's ID and remove it with docker rm -f <container_id>.
![image](https://github.com/user-attachments/assets/1e5e5d96-b3b4-49e6-9e3f-aefca3365b88)
 

  Pushing the Image to Docker Hub:
•	Log in to Docker Hub via the terminal using docker login.

•	Push the image to Docker Hub with docker push <your_dockerhub_username>/node-app:latest.
![image](https://github.com/user-attachments/assets/2d460ec8-6e18-4ebf-8876-961e9b7b4eb3)
 
![image](https://github.com/user-attachments/assets/7dbfb496-d5d2-4a93-9662-f5f7bf48b133)
        

Creating a Kubernetes Cluster:
•	If not already running, start a local Kubernetes cluster using Minikube with the command minikube start.
![image](https://github.com/user-attachments/assets/b8c69819-1142-4c07-92b4-2a8b2f79f21c)
 

Configuring Deployments and Services:
•	Create a deployment.yaml file to define a Kubernetes Deployment that specifies the application’s container image and port configurations.

•	Create a deploymentservice.yaml file to define a LoadBalancer Service, which allows external access to the application.
 ![image](https://github.com/user-attachments/assets/c401a7cd-2616-488c-a4c0-833fb23fcacf)
 ![image](https://github.com/user-attachments/assets/25f45c09-626a-4962-b223-c8f883e74464)

 
 Deploying in Kubernetes:
•	Apply the Deployment and Service configuration files using kubectl apply -f deployment.yaml and kubectl apply -f deploymentservice.yaml.
![image](https://github.com/user-attachments/assets/cacf82c2-0cde-4a42-ab29-2719786c6ae9)
 
Checking the Status:
•	Use kubectl get pods and kubectl get service to ensure that the Pod and Service are running correctly.
![image](https://github.com/user-attachments/assets/cc5c028f-197a-4c5b-803a-eeda801130da)
 
Accessing the Application:
•	Expose the Service using the command minikube service nodeapp-service, which opens the application in a browser.
![image](https://github.com/user-attachments/assets/e0310b63-bf4e-458f-8445-04d156df9a01)
![image](https://github.com/user-attachments/assets/4554c0c1-9744-4bd2-af85-d296aa8aa543)
![image](https://github.com/user-attachments/assets/1d3d0ccc-a0f4-4a27-b933-ce82dea0c9b5)
![image](https://github.com/user-attachments/assets/a40a4e0b-f365-43c2-bd58-357644af6893)
 
    
   
 
### 4. Conclusion:
By following these steps, we've successfully containerized and deployed a Node.js application using Docker and Kubernetes. We built a Docker image, pushed it to Docker Hub, and configured a Kubernetes cluster with deployment and service files. The application is now accessible via a browser, confirming its successful deployment in a Kubernetes environment. This approach enhances scalability, reliability, and easy management of containerized applications. Finally, Kubernetes allows for streamlined automation, making it ideal for managing complex applications in production.

### 5. Result/Output/Writing Summary:
The result of this experiment:
By following these steps, you successfully deploy a Node.js application in a local Kubernetes cluster, demonstrating the power of containerization and orchestration using modern DevOps practices.
