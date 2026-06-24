## Jenkins Demo 1 – Docker Build Automation 
# Objective

Build Docker image automatically using Jenkins.

# workflow

GitHub
 ↓
Jenkins
 ↓
Docker Build
 ↓
Docker Image Created


## Learned
Jenkins Installation
Freestyle Jobs
Git Integration
Build Triggers
Execute Shell
Docker Build
Docker Image Verification


## Commands

docker build -t myweb:v1 .
docker images

## Jenkins Demo 2 – Docker Compose Deployment

# Objective

Deploy multi-container application using Jenkins.

# components
MySQL 8.0
Adminer
Docker Network
Docker Volume
Jenkins
GitHub

## workflow

GitHub
 ↓
Jenkins
 ↓
Clone Repository
 ↓
docker-compose up -d
 ↓
MySQL + Adminer Deployment

## learned

Docker Compose
Multi-container deployments
Volumes
Networks
Jenkins Git Integration
Jenkins Docker Integration
CI/CD Deployment Automation

# problem solved

YAML indentation error
docker-compose.yml vs docker-compose.yaml
Git remote mismatch
Jenkins path issue
docker permission denied
docker-compose not found

# verification
docker ps

# output
jenkins     Up
mysql-db    Up
adminer-ui  Up

