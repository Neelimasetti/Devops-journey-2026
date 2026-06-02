# Python Docker App

## Project Overview

This project demonstrates containerizing a Python Flask application using Docker and running it together with MySQL and Adminer using Docker Compose.

The goal of this project was to understand:

* Dockerfile creation
* Building custom images
* Docker Compose
* Multi-container applications
* Database integration
* Volume persistence

---

## Architecture

```text
Browser
   |
Flask Application
   |
Docker Container
   |
Docker Compose
   |
-------------------------
|         |             |
Python App  MySQL   Adminer
```

---

## Technologies Used

* Python
* Flask
* Docker
* Docker Compose
* MySQL
* Adminer

---

## Application Code

The Flask application exposes a simple web endpoint:

```python
from flask import Flask

app = Flask(__name__)

@app.route("/")
def home():
    return "Hello from Docker Python App"
```

When accessed through the browser, it returns:

```text
Hello from Docker Python App
```

---

## Docker Compose Configuration

The application is deployed using Docker Compose.

Services:

### Python App

* Built using local Dockerfile
* Exposed on port 5000

### MySQL

* Official MySQL image
* Database: devopsdb
* Persistent volume storage

### Adminer

* Browser-based database management tool
* Exposed on port 8080

---

## How to Run

Start all services:

```bash
docker compose up -d
```

Verify:

```bash
docker compose ps
```

Stop services:

```bash
docker compose down
```

---

## Access Application

### Flask Application

```text
http://localhost:5000
```

### Adminer

```text
http://localhost:8080
```

Login:

```text
System: MySQL
Server: mysql
Username: root
Password: mysql123
Database: devopsdb
```

---

## Screenshots

screenshots demonstrating:

* Running containers
* Docker images
* Flask application
* Adminer login
* Database operations

---

## Skills Demonstrated

* Dockerfile creation
* Container management
* Docker Compose
* Multi-container architecture
* Volume persistence
* Database administration
* Application deployment

---

## Learning Outcome

Through this project I learned how to package an application into a container, deploy supporting services using Docker Compose, and manage persistent database storage using Docker volumes.
