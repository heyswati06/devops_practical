# devops_practical
Dockerfiles
==========
All 3 files added - docker compose used to build both nodejs and mongodb containers, with dependencies listed-
docker-compose: It brings up 2 containers for node js service and mongodb service respectively
Dockerfile: details the config for node js container
Run 'docker-compose up' to create both the containers on local machine

 - docker-compose up
 - docker build -t heyswati06/devopspractical_api .
 - docker images
 - docker login
 - docker push heyswati06/devopspractical_api

Information about how you set up the Kubernetes cluster
======================================================
Created the EKS cluster on AWS-
Created a new eks cluster, and attached role+permissions to it
Created a node group, and attached roles+permissions to it

To deploy the app on EKS,  partially created the custom helm-charts but still went through the kubectl route for quickly deploying the app-
- aws eks update-kubeconfig --region ap-northeast-1 --name nodejs-eks
- kubectl create -f C:\Users\MSUSERSL123\Documents\interview_questions\devops-practical\pod.yml
[This pod.yml refers to the same image that is pushed on docker hub]

Non-Functional Requirements-
===========================

[Security taken care using Role Authorization and attaching polices]
[Scalability taken care by adding more replicas-
kubectl scale --replicas=10 deployment
]
[Availability taken care by adding atleast 2 nodes to the nodeGroup]

Screenshots
===========
Most of the SCREENSHOTS added


Note:
====
[Needless to say it can be done using helm charts as well]
I am aware of Terraform and Ansible and have used it on prem for private cloud deployment but not used it here to deploy on EKS, due to time constraint.

