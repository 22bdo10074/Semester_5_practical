## 1. Aim/Overview of the practical: 
To run Node.js application using Docker and manage the Docker volume.
### 2. Objective of this experiment: 
	Learn how to containerize a Node.js application using Docker.

	Understand the role of Docker volumes in persisting data and managing files between containers and the host machine.

	 Run a Docker Node.js application and bind the host machine's port to the container's port.

	 Work with Docker volumes to persist data and manage source code changes in real-time.
### 3.Procedure:
1.	Setup and Install Dependencies

o	Install Node.js (if needed) to create a sample Node.js app.

2.	Write a Sample Node.js Application

o	Create a basic Node.js app (app.js) with Express or a simple HTTP server.

3.	Create a Dockerfile

o	Write a Dockerfile to containerize the Node.js application.

4.	Build and Run the Docker Image

o	Build the Docker image using the docker build command.

o	Run the container using docker run while exposing the necessary ports.

5.	Manage Docker Volumes

o	Use Docker volumes to manage persistent data or hot reload Node.js code.

o	Mount the application source code to the container using Docker volumes.

6.	Test and Verify

o	Test the running Node.js application by visiting http://localhost:3000 in a browser.

o	Modify the source code and verify that changes reflect immediately.
### 4. Steps for the experiment:

1. Set Up a Simple Node.js Application
            1.1. Create a project directory:
                   Commands: mkdir my-node-app
                                        cd my-node-app
 
![image](https://github.com/user-attachments/assets/49ae2903-045a-456b-a359-17ecbc23db05)


          1.2. Initialize the Node.js application:
                  Command: npm init -y
![image](https://github.com/user-attachments/assets/d03ba957-4c93-4fdb-9e12-bd51e558c532)
               
 
 This command creates a package.json file with default configurations.

           1.3. Create a simple app.js file:
                  Command: touch app.js
Open app.js with your favorite editor (e.g., nano or vim), and add the following code:

// app.js
const http = require('http');
const hostname = '0.0.0.0';
const port = 3000;
const server = http.createServer((req, res) => {
res.statusCode = 200;

  res.setHeader('Content-Type', 'text/plain');
  res.end('Hello, Docker World!\n');
});

This is a basic Node.js application that will respond with "Hello, Docker World!" on port 3000.

3. Create a Dockerfile
    Now, let's create a Dockerfile that Docker will use to build the image for your Node.js      application.
    Command: touch Dockerfile

Open the Dockerfile and add the following code:
![image](https://github.com/user-attachments/assets/6d81328c-1281-4a5a-9fa9-848fca0032da)

 

 4.  Build the Docker Image
       Now, it's time to build the Docker image for your Node.js application.

        Command: docker build -t my-node-app .
This command tells Docker to build an image using the Dockerfile in the current directory    and tag it as my-node-app.

![image](https://github.com/user-attachments/assets/9f5c3248-81c6-42f7-888e-7982d9d85b68)

 

5. Run the Docker Container
Once the image is built, you can run the container. We'll map the container's port 3000 to the host's port 3000.
             Command: docker run -p 3000:3000 my-node-app
 
![image](https://github.com/user-attachments/assets/1175928a-4906-4ebe-bc77-3a0e4ff94521)

6.Now, if you navigate to http://localhost:3000 in your browser or use curl:
Command: http://0.0.0.0:3000/
You should see the response: Hello, Docker World!
![image](https://github.com/user-attachments/assets/5d01fdfd-19d9-4242-9340-60e10d0892c9)

 
7.Pushing a Docker image to the Docker hub.

 ![image](https://github.com/user-attachments/assets/67a6a97e-0b14-450b-b9f1-b54aca3cf9e6)

 ![image](https://github.com/user-attachments/assets/0f8fd301-9793-48f4-b0fe-abd1ae87b6c9)


 Now, you need to log in docker hub with your username, password and then you can see the pushed images.
 ![image](https://github.com/user-attachments/assets/a0688b8a-ec09-4bc4-9608-716973def761)


### 8. Result/Output/Writing Summary:
   The result of this experiment achieved its objectives by:

•	Demonstrating how to run a Node.js application in a Docker container.

•	Illustrating the benefits of using Docker volumes for development.

•	Enabling sharing and deployment of the application via Docker Hub.
