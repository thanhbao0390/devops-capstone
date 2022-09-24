[![CircleCI](https://circleci.com/gh/thanhbao0390/devops-capstone.svg?style=svg)](https://circleci.com/gh/thanhbao0390/devops-capstone)

# devops-capstone
The final CAPSTONE project

## Table of contents
* [General info](#general-info)
* [Folder structure](#folder-structure)
* [Tools](#technologies)
* [Usage](#setup)
* [Result](#result)

## General info
CI/CD pipeline for deploying and linting a microservices application NGINX using Rolling Deployment. Pipeline will containerize application and push the docker image to the Docker Hub.  After that it will create the AWS network infrastructure required to deploy the applicion, AWS EKS Cluster & Nodes and it will deploy application to the EKS Cluster.

## Folder structure
* nginx-hello : Source Files
* iaac : Infrastructure as a code - Deployment Files
* .circleci : Configuration File for CircleCI & Kubernetes deployment and service files
	
## Tools
Project is created with:

* CirleCI
* CloudFormation
* AWS
* Kubernetes
* Docker Hub
* GitHub
	
## Usage
To run this project in CircleCI, you have to:

* Fork the project to your Github Account
* Setup and Configure CirceCI account with Github and AWS Credentials
* Setup DockerHub account. Save username and password to your local computer, you will need it.
* AWS : configure default VPC  and Key Pair. Store Access key id and secret access key to your local computer, you will need it.
* Configure enviroment variables AWS_DEAFULT_REGION, AWS_ACCESS_KEY_ID, AWS_SECRET_ACCESS_KEY, DOCKERHUB_PASSWORD, DOCKERHUB_USERNAME in your CircleCI account
* Change SSHKeyName Value with your AWS Key Pair name (ec2-params.json)
* Use imageid compliant with your AWS Region (ec2-params.json)
* Change the build job from config.yml in order to include your DockerHub credentials, for example :

```
ddocker build -t thanhbao0390/devops-capstone .
docker tag nginx-hello:latest ${DOCKERHUB_USERNAME}/nginx-hello:latest
docker push thanhbao0390/devops-capstone

```


## Result 
LoadBalancer URL:


