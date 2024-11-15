## 1. Aim/Overview of the practical: 
  ### To Setup
          i.      Container to WWW Communication,
         ii.      Container to Local Host Machine Communication,
       iii.      Container to Container Communication,
       iv.      Creating a Container & Communicating to the Web (WWW),
        v.      Container to Host Communication Work,
       vi.      Container to Container Communication using Docker Desktop.
### 2. Objective of this experiment: 
The objective of this experiment is to understand and set up different types of communication involving Docker containers, which are fundamental concepts in containerized applications. By exploring the following communication methods, you'll gain practical insights into how containers interact with external networks, the host machine, and other containers within a Docker environment.

### 3.Procedure:
   #### i.     Procedure for the Container to WWW Communication:
Step 1: Pull an Nginx image from Docker Hub (a popular web server) to create a web server container:

Step 2: Pull the Nginx image:
           $ docker pull nginx

Step 3: Create a Docker container using the Nginx image:
          $ docker run -d --name my_web_app -p 80:80 nginx

Step 4: Verify that the container is running:
          $ docker ps
You should see the "my_web_app" container listed among the running containers.

Step 5: Access the web server running inside the container:
         Open your web browser and enter http://localhost in the address bar.
If you see the default Nginx welcome page, it means the communication between the container and the WWW is successful.
![image](https://github.com/user-attachments/assets/830eccc1-e9d4-4207-841a-e4140d73558c)

![image](https://github.com/user-attachments/assets/b92c94c9-7929-4381-b4c0-3f075d597d08)


 

This procedure demonstrates how to set up a simple web server container using Nginx and communicate with the WWW through Docker Desktop.

#### ii.     Procedure for Container to Local Host Machine Communication:

Step 1: Identify the service running on the host machine that you want to communicate with from the container.

Step 2: Determine the IP address of the host machine:
            On Linux/macOS, open a terminal and run the command:
            $ ifconfig
            On Windows, open a command prompt and run the command:
            $ ipconfig
 
 ![image](https://github.com/user-attachments/assets/58fcabe5-94e7-4369-aa11-c4041ab9409f)


Step 3: Create a Docker container and configure it to communicate with the host machine: 
           Open your terminal or command prompt and run the following command:
           docker run -d --name my_local_app --add-host host_machine:<host_ip_address> 

Step 4: Verify that the container is running:
             $ docker ps


 ![image](https://github.com/user-attachments/assets/02ea49e2-e8f7-416e-8b22-8b09698a8712)

             
Step 5: Test the container's communication with the host machine:

Run the following command to access a service (e.g., a web server) running on the   host machine from within the container:
$ docker exec my_local_app curl http://host_machine
![image](https://github.com/user-attachments/assets/0617eff0-18d9-462d-a125-055faec11a79)
 
   
This allows for seamless integration and interaction between containerized applications and the host environment.

#### iii. Procedure for Container-to-Container Communication:

Step 1: Create two Docker containers that need to communicate with each other:
Open your terminal or command prompt.

Step 2: Run the first container:
             $ docker run -d --name container1 nginx

Step 3: Run the second container:
             $ docker run -d --name container2 nginx
    
 
![image](https://github.com/user-attachments/assets/e53cef78-3759-41a8-8f2f-fa39e07c63a0)


Step 4: Verify that both containers are running:
             $ docker ps
 You should see "container1" and "container2" listed among the running containers.

![image](https://github.com/user-attachments/assets/20ab7bc9-7c46-4418-924f-acdef5ec90f8)
 

Step 5: Create a user-defined bridge network:
             $ docker network create my_network

Step 6: Attach both containers to the user-defined network:
             $ docker network connect my_network container1
            $ docker network connect my_network container2

Step 7: Verify that both containers are connected to the same network:
             $ docker network inspect my_network

![image](https://github.com/user-attachments/assets/aa20cdc8-7439-4b2b-bdde-cddafc761295)
 

Step 8: Test the communication between the containers:
             Run the following command inside "container1" to ping "container2":
              $ docker exec container1 ping container2
 ![image](https://github.com/user-attachments/assets/7122d9e5-64aa-4fc1-bf54-d353ffc3876b)


Step 9: Clean up (optional):
If you want to stop and remove the containers and the user-defined network after testing, run the following commands:

              $ docker stop container1 container2
              $ docker rm container1 container2
              $ docker network rm my_network

 ![image](https://github.com/user-attachments/assets/af5e2774-0c6f-41bc-aa25-48e8e7a8d671)


#### iv. Procedure for Container to Host Communication Work:

Step 1: Identify the service running on the host machine that you want to communicate with from the container.

Step 2: Create a Docker container and configure it to communicate with the host service:
             $ docker run -d --name my_container -p 8080:80 nginx
     
Step 3: Verify that the container is running:
             $ docker ps
    
![image](https://github.com/user-attachments/assets/346ee153-5acb-4ef7-9196-79196b2ff863)

Step 4: Access the service running on the host from the container:
Inside the container, you can now access the web server running on the host machine using the host IP address and the mapped port (8080).
To find the IP address of the host, you can use the following command:
              $ ifconfig    # Linux/macOS
              $ ipconfig    # Windows

 
![image](https://github.com/user-attachments/assets/28a4584e-64f2-49d1-a5e6-90d6ad7e63de)

Step 5: Test the communication from the container to the host service:
Open a terminal inside the container:
$ docker exec -it my_container /bin/bash
![image](https://github.com/user-attachments/assets/56ead444-2106-4d72-8e18-e06612cb2c03)

 

Step 6. You should see the response from the web server running on the host.
/bin/bash: The command to run inside the container, in this case, we are using the bash shell. 


### 8. Result/Output/Writing Summary:
The result of this experiment achieved its objectives by:
This procedure demonstrates how to set up communication between two Docker containers using Docker Desktop. 
By connecting both containers to a user-defined bridge network, you can enable them to interact with each other. 
This type of communication is valuable when building complex applications that consist of multiple interconnected containers.
