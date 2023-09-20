

 # Deploying a Node.js App Using Docker and EC2
============================================

In this comprehensive guide, I will walk you through the process of deploying a Node.js application using Docker on an Amazon EC2 instance. WIe will also discuss the app's functionality briefly.

Application Functionality
-------------------------
 The sample project I was working on includes mock data used in an API. The API is a simple RESTful service with a "GET" endpoint `/api/users` that retrieves user data from a JSON file containing mock data. This application will serve as our example for containerization and deployment.



Deployment Process Overview
---------------------------

Now, let's outline the steps we'll follow to deploy our Node.js application using Docker on an Amazon EC2 instance, coupled with GitHub Actions:

1.  **GitHub Actions Workflow**: We will create a CI/CD workflow using GitHub Actions to automate the deployment process.
https://github.com/jesusverma/m22aie203/actions

    
2.  **Dockerization**: We'll create a Dockerfile for our Node.js application, specifying the base Node.js image, setting a working directory, copying necessary files, installing dependencies, and exposing the application port.
https://hub.docker.com/r/jesusverma/node-app-docker-ec2
    
3.  **GitHub Actions Build Job**: The build job will build a Docker image from our repository and publish it to Docker Hub. We'll set up secret variables for Docker Hub credentials.
https://github.com/jesusverma/m22aie203/actions/runs/6247670520/job/16961765541
    
4.  **AWS EC2 Instance**: We'll host our self-hosted runner on an AWS EC2 instance, which will be used for deploying the application.
http://3.85.133.46
    
5.  **GitHub Actions Deploy Job**: The deploy job will run on the EC2 instance and pull the Docker image from Docker Hub, ensuring the latest version is used. We'll also handle any existing containers and start our application container.
https://github.com/jesusverma/m22aie203/actions

6.  **Security Group Rules**: We will configure the AWS Security Group to allow traffic on the exposed port (5000 in this case) to make the application accessible.
    

Rest API Endpoint for get all users:  http://3.85.133.46:5000/rest/getAllUsers


## Author
### Jesus Verma - M22AIE203


