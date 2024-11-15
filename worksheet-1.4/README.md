## 1. Aim/Overview of the practical: 
To manage Volumes and Containers for storing and retrieval of data in Docker.
### 2. Objective of this experiment: 
To focus on understanding and working with Docker volumes.

•   To create and manage volumes

•   Learn to create a container that uses a volume to store and retrieve data.
### 3. Procedure:

Volumes in Docker are used to store and share persistent data between Docker containers. They are independent of the container lifecycle, meaning that they are not deleted when the container stops or is removed, making them useful for managing persistent data. This procedure outlines the steps to create, manage, and use volumes and containers in Docker.

### 4. Steps for the experiment:

1. Creating Docker Volume

To create a Docker Volume, you can use the Volume Create command as shown below.
Sudo docker volume create vol-demo

![image](https://github.com/user-attachments/assets/e0ac88a3-f2bc-4cdd-951c-454c76e9967e)

 
 
2. Mounting Volume with a Container
After you have created a Volume, you can mount it with a Docker Container -v flag along with the Docker run command.
Sudo docker run -it -v <volume-path-in-local-machine>:<dest-path-in-container> <image-name>
To verify if the volume has been successfully mounted or not, you can move to the destination directory inside the Container.
![image](https://github.com/user-attachments/assets/366780af-cbc7-4f51-8bc0-fdfff610d3c4)

 

3. Listing all the Docker Volumes
You can list all your Docker Volumes using the Docker Volume ls command.
Sudo docker volume ls
![image](https://github.com/user-attachments/assets/7bdef3b2-3f25-4e4e-8ad0-65a34a2d4c47)
 
4. Inspecting Docker Volumes
You can get the details of your Docker Volumes using the Volume Inspect Command.
Sudo docker volume inspect <volume-name>
![image](https://github.com/user-attachments/assets/e38c1b20-5b7d-4417-8704-7b1b767ef0f1)

 

5. Removing specific Docker Volume
To remove a particular Docker Volume, you can specify the name in the Docker Volume rm command.
Sudo docker volume rm <volume-name>
![image](https://github.com/user-attachments/assets/12fdf467-d335-4e72-9dfd-f61b03d8abf7)
![image](https://github.com/user-attachments/assets/7bd90e8c-98e2-4557-b6b1-c7523c4bc5fd)

 

 
6. Removing all the Docker Volumes
To remove all the Docker volumes together, you can use the following command. Note that before removing a Docker Volume, you need to make sure that it is not mounted to any Container.
Sudo docker volume rm $(sudo docker volume ls -q)
![image](https://github.com/user-attachments/assets/2d6b2206-87bd-4279-956e-b24b2055297e)
![image](https://github.com/user-attachments/assets/eb1b37cb-07df-4291-a9f9-4024ee36cc75)
 
 
To verify whether all the volumes have been deleted or not, you can use the Volume list command.
sudo docker volume ls
![image](https://github.com/user-attachments/assets/c3c5c961-5643-43fb-9754-50c7513ab4ed)
 

7.Create a Docker volume and specify a host directory.
To create a Docker volume and specify a host directory, you can use the -v flag to bind the host directory to the container. For example, the following command mounts the host directory /path/on/host to /data in the container:
Example- docker run -d --name my_container -v /path/on/host:/data ubuntu

This will ensure that any changes made inside /data in the container will be reflected in the host directory and vice versa. The data in this host directory will persist even if the container is stopped or removed.
![image](https://github.com/user-attachments/assets/d92052df-9428-42d4-b8b2-e1535b1d1a01)
 
![image](https://github.com/user-attachments/assets/7dd716a3-2616-44c2-b310-3f5e4c065649)


 


### 5. Result/Output/Writing Summary:
When managing volumes and containers for storing and retrieving data in Docker, the expected results of this practical are as follows:
 volume creation, volume mounting, Data persistence, Data sharing between containers, volume inspection and volume cleanup.
