# Udacity Cloud DevOps Capstone Project

Jenkins pipeline for blue green deployment using AWS EKS — Kubernetes — Docker — Capstone project, Cloud DevOps Nanodegree .

## Project Overview

In this project I have apply my skills and knowledge which were developed throughout the Cloud DevOps Nanodegree program. These include:

-   Working in AWS
-   Using Jenkins to implement Continuous Integration and Continuous Deployment
-   Building pipelines
-   Working with Ansible and CloudFormation to deploy clusters
-   Building Kubernetes clusters
-   Building Docker containers in pipelines


## Project Files

#### infra

Contains all the files related to infrastructure deployment.

-   `jenkins-server-parameters.json`: Parameters file for cloud formation stack.
-   `jenkins-server.yml`: CloudFormation template for creating jenkins server.
-   `Jenkinsfile`: Jenkinsfile for creating EKS cluster and configuring kubectl.
-   `create.sh`: create cloud formation stack.
-   `update.sh`: updated cloud formation stack.
-   `delete.sh`: delete cloud formation stack.


#### kubernetes

Contains all template files for Kubernetes resources.

-   `blue_deployment.yml`: A replication controller template that creates pods with label as `app=capstoneblue`.
-   `blue_service.yml`: A service template that selects all the pods with label as `app=capstoneblue`.
-   `green_deployment.yml`: A replication controller template that creates pods with label as `app=capstonegreen`.
-   `green_service.yml`: A service template that selects all the pods with label as `app=capstonegreen`.

#### screenshots

Contains all screenshots taken during creation of this project.

#### Dockerfile

This is Dockerfile of application.

#### index.html

This is main html file of application.

#### Jenkinsfile

This file contains the steps of CICD pipeline of application.

