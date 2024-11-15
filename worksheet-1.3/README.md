## 1. Aim/Overview of the practical: 
 ### To understand Container Creation and Execution:
1.     Install docker on Linux/windows
2.     Pull a Docker image from Docker Hub.
3.     Run a container from the pulled image.
4.     Explore container logs and check the running processes inside the container.
5.     Stop and remove the container.

### 2. Task to be done: 
The objective of this experiment is to provide hands-on experience with Docker, a popular containerization platform, by guiding you through the fundamental tasks of container creation, management, and exploration. Specifically, the goals . 
### 3. Apparatus:
	Computer or VM with Linux/Windows

	Internet Connection

	Docker Software (Docker Engine or Docker Desktop)

	Text Editor or IDE

	Terminal/Command Prompt: for writing commands. 

	Docker Hub Account: For pushing and pulling Docker images (optional, for repository-related tasks).

### 4. Steps for the experiment:
Here’s a step-by-step guide for working with Docker, covering everything from checking the Docker version to pushing an image to Docker Hub.
I.	Check Docker Version:
   • Command: docker –version
   • Purpose: This command checks and displays the current version of Docker installed on your system.
 ![image](https://github.com/user-attachments/assets/46d32956-7fa3-49d3-9c1a-61f691c3ad3a)

          
II.	View Docker Images:
•	Command: docker images
•	Purpose: Lists all Docker images available on your local system. 
 ![image](https://github.com/user-attachments/assets/4de21609-ecef-4df6-8f37-7e02900ecd1d)

                      
III.	Pull a Docker Image
•	Command: docker pull <image_name>
•	Example: docker pull ubuntu:latest
•	Purpose: Downloads the specified Docker image from DockerHub to your local system.
 ![image](https://github.com/user-attachments/assets/88f77dc5-5ab4-477e-abee-100c0d48644b)


IV.	Create a Container
•	Command: docker create --name <container_name> <image_name>
•	Example: docker create --name my_ubuntu_container ubuntu:latest
•	Purpose: Creates a container from the specified image without starting it.
 ![image](https://github.com/user-attachments/assets/aae82595-58d2-4fcd-8f8c-310b1b3a961d)

V.	Start a Container
•	Command: docker start <container_name>
•	Example: docker start my_ubuntu_container
•	Purpose: Starts the specified container.

VI.	 Run and Create a Container
•	Command: docker run -dit --name <container_name> <image_name>
•	Example: docker run -dit --name my_ubuntu_container ubuntu:latest
•	Purpose: Creates and starts a container in the background with interactive mode enabled.
VII.	 List All Containers
•	Command: docker ps -a
•	Purpose: Lists all containers on your system, including both running and stopped ones.
 ![image](https://github.com/user-attachments/assets/c81d4007-3958-4c3b-b750-83d54433d78a)

VIII.	 Pause a Container
•	Command: docker pause <container_name>
•	Example: docker pause my_ubuntu_container
•	Purpose: Pauses the execution of the specified running container.

IX.	Unpause a Container
•	Command: docker unpause <container_name>
•	Example: docker unpause my_ubuntu_container
•	Purpose: Resumes the execution of a paused container.

X.	 Start All Containers
•	Command: docker start $(docker ps -aq)
•	Purpose: Starts all containers that are currently stopped.

XI.	11. Stop All Containers
•	Command: docker stop $(docker ps -aq)
•	Purpose: Stops all running containers.

XII.	 Remove a Stopped Container
•	Command: docker rm <container_name>
•	Example: docker rm my_ubuntu_container
•	Purpose: Removes a specific stopped container from your system.

XIII.	 Remove All Stopped Containers
•	Command: docker rm $(docker ps -aq)
•	Purpose: Removes all stopped containers from your system.
![image](https://github.com/user-attachments/assets/7e7946c4-fcf1-4830-bfdc-fc6b054514be)

 
XIV.	Kill a Running Container
•	Command: docker kill <container_name>
•	Purpose: Immediately terminates a running container.

XV.	Login to DockerHub
•	Command: docker login
•	Purpose: Authenticates your local Docker client with DockerHub, enabling you to push images to the DockerHub repository.
![image](https://github.com/user-attachments/assets/88d1a6c9-758b-437f-ac3b-b93921bd667c)

 
XVI.	Push an Image to DockerHub
•	Command: docker push <user_name>/<image_name>:<tagname>
•	Example: docker push sandhya76/ubuntu:latest
•	Purpose: Uploads a local Docker image to DockerHub under your account.
![image](https://github.com/user-attachments/assets/eca20537-25cd-4300-95c4-8570320ca2e7)

 

### 7. Result/Output/Writing Summary:
	Initial Setup: Ensure Docker is installed and working (steps 1 and 2).

	Image Management: Pull, view, and manage Docker images (steps 3, 4, 16).

	Container Management: Create, start, run, pause, unpause, stop, and remove containers (steps 5 to 14).

	DockerHub Interaction: Log in and push images to DockerHub (steps 15 and 16).
 
![image](https://github.com/user-attachments/assets/255f315d-2d02-4c3f-8f10-8ff12b45a208)

