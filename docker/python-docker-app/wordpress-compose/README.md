# WordPress Deployment with Docker Compose

## Project Overview

This project demonstrates deploying a WordPress application using Docker Compose.

The setup includes:

* WordPress Container
* MySQL Database Container
* Docker Volume for persistent storage
* Docker Network for container communication

The goal of this project was to understand how multiple containers can work together as a single application.

---

## Architecture

Browser
|
WordPress Container
|
Docker Network
|
MySQL Container
|
Docker Volume

---

## Technologies Used

* Docker
* Docker Compose
* WordPress
* MySQL
* Docker Volumes
* Docker Networks

---

## Services

### MySQL

Database service responsible for storing:

* WordPress data
* User information
* Posts
* Configuration

Configuration:

* Database: wordpress
* User: wpuser
* Password: wppass

Persistent storage is provided using:

```yaml
dbdata:/var/lib/mysql
```

---

### WordPress

WordPress application container.

Connected to MySQL using:

```yaml
WORDPRESS_DB_HOST=db
```

Exposed through:

```yaml
8085:80
```

Access:

```text
http://localhost:8085
```

---

## Docker Compose Features

### Multi-Container Deployment

Docker Compose starts all services together.

```bash
docker compose up -d
```

---

### Container Communication

Containers communicate using:

```yaml
wp-network
```

This removes the need to manually configure IP addresses.

---

### Persistent Storage

Data remains available even after container restart.

Volume used:

```yaml
dbdata
```

---

## How to Run

Start application:

```bash
docker compose up -d
```

Verify:

```bash
docker compose ps
```

Stop:

```bash
docker compose down
```

---

## Access Application

WordPress:

```text
http://localhost:8085
```

Browser should display the WordPress setup page.

---

## Skills Demonstrated

* Docker Compose
* Multi-container applications
* MySQL integration
* Container networking
* Volume management
* Service dependencies
* Application deployment

---

## Learning Outcome

Through this project I learned how Docker Compose simplifies the deployment of multi-container applications and how services communicate using networks and persistent volumes.

This project helped me understand real-world containerized application deployment using WordPress and MySQL.
