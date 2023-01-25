
## Problem Statement

The goal of this project is to:

-   Dockerize a node js sample application
-   Deploy MongoDB as a separate Docker container
-   Create a Kubernetes cluster to deploy the application using EKS
-   Deploy the application to the Kubernetes cluster using Helm Charts, Kubectl and Terraform

## Getting Started

### Step 1: Dockerfiles

-   All 3 docker related files have been added and then docker compose is used to build both the nodejs and mongodb containers, with their dependencies
-   `docker-compose.yml` brings up 2 containers for the node js service and mongodb service respectively
-   `Dockerfile` contains the configuration for the node js container
-   Run the following commands to create both the containers on the local machine, build the image and push it to Docker Hub:
    -   `docker-compose up`
    -   `docker build -t heyswati06/devopspractical_api .`
    -   `docker images`
    -   `docker login`
    -   `docker push heyswati06/devopspractical_api`

### Step 2: Setting up the Kubernetes Cluster on EKS

-   Created a new EKS cluster on AWS
-   Attached role+permissions to the cluster
-   Created a node group for the cluster and attached roles+permissions to it

### Step 3: Deploying the App on EKS

-   Updated the kubeconfig file by running `aws eks update-kubeconfig --region ap-northeast-1 --name nodejs-eks`
-   Deployed the app on the cluster using `kubectl` by running `kubectl create -f pod.yml` 
(*`pod.yml` refers to the same image that has been pushed on Docker Hub*)

## Non-Functional Requirements

-   Security: Taken care using Role Authorization and attaching policies
-   Scalability: Taken care by adding more replicas - `kubectl scale --replicas=10 deployment`
-   Availability: Taken care by adding at least 2 nodes to the nodeGroup

**Note**: Will be trying out step 3 using Helm Charts, Terraform and Ansible approaches as well, and keep updating this repo.
