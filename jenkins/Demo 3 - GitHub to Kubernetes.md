# Demo 3 – GitHub → Jenkins → Kubernetes Deployment

## Objective
Automate Kubernetes deployment using Jenkins. Jenkins pulls the code from GitHub and deploys it into a Kubernetes cluster using kubectl.

---

## Architecture

GitHub Repository
        │
        ▼
Jenkins Freestyle Job
        │
Execute Shell
        │
kubectl apply
        │
        ▼
Kubernetes Cluster (Minikube)
        │
Deployment + Service
        │
        ▼
Application Accessible

---

## Workflow

Developer
   │
git push
   │
   ▼
GitHub Repository
   │
   ▼
Jenkins
   │
Git Clone
   │
Execute Shell
   │
├── kubectl apply -f deployment.yaml
└── kubectl apply -f service.yaml
   │
   ▼
Minikube Cluster
   │
Deployment
   │
ReplicaSet
   │
Pods
   │
Service
   │
Browser

---

## Project Structure

github-to-k8s-demo/
│
├── deployment.yaml
└── service.yaml

---

## deployment.yaml

Purpose:
Creates a Deployment in Kubernetes.

Responsibilities:
- Creates Pods
- Maintains desired number of replicas
- Self-healing
- Rolling updates
- Rollbacks

Example:

apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-github-demo

spec:
  replicas: 2

  selector:
    matchLabels:
      app: nginx

  template:
    metadata:
      labels:
        app: nginx

    spec:
      containers:
      - name: nginx
        image: nginx

---

## service.yaml

Purpose:
Expose Pods using a Service.

Example:

apiVersion: v1
kind: Service

metadata:
  name: nginx-github-service

spec:
  type: NodePort

NodePort allows the application to be accessed from outside the Kubernetes cluster.

---

## Jenkins Job Configuration

Job Type:
Freestyle Project

Repository:
https://github.com/Neelimasetti/github-to-k8s-demo.git

Source Code Management:
Git

Build Step:
Execute Shell

---

## Build Script

echo "Starting Kubernetes Deployment"

pwd

ls -la

kubectl apply -f deployment.yaml

kubectl apply -f service.yaml

kubectl get deployment

kubectl get pods

kubectl get svc

echo "Deployment Completed Successfully"

---

## Command Explanation

pwd
Displays the current working directory.

Example:
/var/lib/jenkins/workspace/github-to-k8s-job

------------------------------------------------

ls -la
Lists all files in the Jenkins workspace.

Expected Files:
deployment.yaml
service.yaml

------------------------------------------------

kubectl apply -f deployment.yaml

Creates or updates the Deployment.

------------------------------------------------

kubectl apply -f service.yaml

Creates or updates the Service.

------------------------------------------------

kubectl get deployment

Displays deployment status.

Example:

NAME                  READY   AVAILABLE
nginx-github-demo     2/2     2

------------------------------------------------

kubectl get pods

Displays Pod status.

Example:

nginx-github-demo-xxxxx    Running
nginx-github-demo-yyyyy    Running

------------------------------------------------

kubectl get svc

Displays Service information.

Example:

NAME                    TYPE       PORT
nginx-github-service    NodePort   30081

---

## Verification Commands

kubectl get deployment nginx-github-demo

kubectl get pods

kubectl get svc nginx-github-service

minikube service nginx-github-service

Expected Result:

Welcome to nginx!

---

## Final Output

Deployment:
READY 2/2

Pods:
2 Running Pods

Service:
NodePort Created

Application:
Nginx Welcome Page displayed successfully.

Jenkins Build:
Finished: SUCCESS

---

## Real-World Workflow

Without Jenkins

Developer
↓

SSH into Server

↓

kubectl apply

Manual Deployment

------------------------------------------------

With Jenkins

Developer

↓

git push

↓

GitHub

↓

Webhook

↓

Jenkins

↓

CI Pipeline

↓

Docker Build (if required)

↓

Docker Registry (if required)

↓

kubectl apply

↓

Kubernetes Deployment

Fully Automated Deployment

---

## Problems Faced During Demo

1. Jenkins Docker Container

Problem:
kubectl was unable to communicate with Minikube correctly.

Reason:
Docker networking limitations in WSL2.

Solution:
Installed Native Jenkins.

------------------------------------------------

2. Java Version

Problem:
Latest Jenkins does not support Java 17.

Solution:
Installed OpenJDK 21.

Verified using:

java -version

------------------------------------------------

3. Jenkins Repository GPG Key

Problem:
Repository signing key error (NO_PUBKEY)

Solution:
Imported the latest Jenkins repository key.

------------------------------------------------

4. Docker Permission

Problem:
Jenkins user could not execute Docker commands.

Solution:

sudo usermod -aG docker jenkins

Verification:

sudo -u jenkins docker ps

------------------------------------------------

5. Kubernetes Permission

Copied

~/.kube

and

~/.minikube

to

/var/lib/jenkins/

Updated kubeconfig paths from

/home/pcneelima

to

/var/lib/jenkins

Verified:

sudo -u jenkins kubectl get nodes

Output:

minikube Ready

---

## Interview Questions

Q1. Why do we use Jenkins?

Jenkins automates Continuous Integration and Continuous Deployment by building, testing, and deploying applications automatically.

------------------------------------------------

Q2. Why use Deployment instead of Pod?

Deployment provides:
- Self-healing
- Scaling
- Rolling Updates
- Rollbacks

Pods alone do not provide these features.

------------------------------------------------

Q3. Why do we need a Service?

Pods have dynamic IP addresses. A Service provides a stable endpoint to access the application.

------------------------------------------------

Q4. Why use NodePort?

NodePort exposes the application outside the Kubernetes cluster for testing and development.

------------------------------------------------

Q5. What does kubectl apply do?

Creates a resource if it does not exist.
Updates the resource if it already exists.

---

## Key Learning

In this demo, Jenkins cloned the code from GitHub and automatically deployed Kubernetes resources using kubectl apply. The deployment created two Nginx Pods managed by a Deployment and exposed them using a NodePort Service. The application was successfully accessed in a browser using Minikube, demonstrating a complete GitHub → Jenkins → Kubernetes CI/CD workflow.

---

## Commands Used

kubectl apply -f deployment.yaml

kubectl apply -f service.yaml

kubectl get deployment

kubectl get pods

kubectl get svc

minikube service nginx-github-service

sudo -u jenkins kubectl get nodes

sudo -u jenkins docker ps

---

## Demo Status

✅ GitHub Repository Created

✅ Jenkins Freestyle Job Created

✅ Git Repository Connected

✅ Jenkins Cloned Repository

✅ Deployment Created

✅ Service Created

✅ Pods Running

✅ NodePort Created

✅ Application Accessible

✅ Jenkins Build SUCCESS

✅ Demo 3 Completed Successfully

