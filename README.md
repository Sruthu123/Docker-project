**Overview**

In this project, we’ll create a containerize web application and deploy it on Google Cloud.

The project involves:
    1.	Writing a simple web application.
    2.	Creating a Dockerfile that defines how to build the container.
    3.	Pushing the container image to Google Container Registry.
    4.	Deploying the container on Google Cloud Run to make it publicly accessible.

**Prerequisites**

You will need the following tools:

•	Google Cloud SDK

•	Google Cloud Account

•	Docker

•	Git

**Steps to Containerize the Application**

Step 1: Code Your App

Step 2: Create Dockerfile

        A Dockerfile is a script that contains a set of instructions to automate the process of building a Docker image.

        Dockerfile is used to:
        
        1.	Define the Base Image: This is the starting point for your container. It could be a minimal operating system or             an application-specific image like Python, Node.js, etc.

            FROM python:3.7-slim

        2.	Install Dependencies: The Dockerfile specifies the necessary packages and libraries that need to be installed               inside the container to run your application.
        
            WORKDIR $APP_HOME

        3.	Copy Files: It allows you to copy application code, configuration files, or assets from your local system into              the container's file system.

            COPY ../ 

        4.	Set Environment Variables: You can specify any environment variables that the application may need to run                   (e.g., database URLs, secret keys, etc.).
        
        5.	Expose Ports: Specifies which ports the container will listen on, allowing you to interact with the application             (e.g., web servers typically expose port 80 or 8080).
        
        6.	Define Commands to Run: The CMD or ENTRYPOINT instruction defines the default command to run when the container             starts (for example, starting a web server).

            CMD exec gunicorn --bind:$PORT --workers 1 --threads 8 --timeout 0 app:app 
            
Step 3: Build container image

	      Build process for container images
       
	      Command to build image: gcloud builds submit --tag gcr.io/docker-environment-442007/container-image
       
Step 4: Enable API

Step 5: Deploy container image on cloud run

	      Command for Run and deploy : gcloud run deploy –image gcr.io/set up a virtualized environment using Docker/      container_image


