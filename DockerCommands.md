# Docker Commands Documentation

## Setup & Initialization

### **1. Initialize a Git Branch for Docker Work**

```bash
git checkout -b docker-assignment
```

**Purpose:** Creates a separate branch for Docker implementation.

---

##  Building and Running Containers

### **2. Build Backend Image**

```bash
docker build -t ashikahammad/my-backend:latest ./backend
```

**Purpose:** Builds the backend Docker image using the `Dockerfile` inside `backend/`.

### **3. Build Frontend Image**

```bash
docker build -t ashikahammad/my-frontend:latest ./frontend
```

**Purpose:** Builds the frontend Docker image using the `Dockerfile` inside `frontend/`.

### **4. Run Backend Container**

```bash
docker run -d --name backend -p 5050:5050 --network mern ashikahammad/my-backend:latest
```

**Purpose:** Runs the backend container in detached mode, exposing port 5050.

### **5. Run Frontend Container**

```bash
docker run -d --name frontend -p 5173:5173 --network mern ashikahammad/my-frontend:latest
```

**Purpose:** Runs the frontend container in detached mode, exposing port 5173.

### **6. Run MongoDB Container**

```bash
docker run -d --name mongodb -p 27017:27017 --network mern -v mongo-data:/data/db mongo:latest
```

**Purpose:** Runs a MongoDB container with volume mapping for data persistence.

---

##  Using Docker Compose

### **7. Build and Start All Services (Backend, Frontend, MongoDB)**

```bash
docker-compose up -d --build
```

**Purpose:** Builds and starts all services defined in `docker-compose.yml` in detached mode.

### **8. Stop All Services**

```bash
docker-compose down
```

**Purpose:** Stops and removes all running containers defined in `docker-compose.yml`.

### **9. View Running Containers**

```bash
docker ps
```

**Purpose:** Lists all running containers and their details.

---

##  Debugging & Monitoring

### **10. View Logs of a Running Container**

```bash
docker logs -f backend
```

**Purpose:** Shows real-time logs of the `backend` container.

### **11. Check Health Status of Containers**

```bash
docker inspect --format='{{json .State.Health}}' backend
```

**Purpose:** Displays the health status of the `backend` container.

### **12. Open an Interactive Shell in a Container**

```bash
docker exec -it backend /bin/sh
```

**Purpose:** Opens a shell inside the running `backend` container for debugging.

---

##  Pushing Images to Docker Hub

### **13. Log in to Docker Hub**

```bash
docker login
```

**Purpose:** Authenticates with Docker Hub.

### **14. Tag Docker Images**

```bash
docker tag ashikahammad/my-backend:latest ashikahammad/my-backend:latest
docker tag ashikahammad/my-frontend:latest ashikahammad/my-frontend:latest
```

**Purpose:** Tags images before pushing them to Docker Hub.

### **15. Push Docker Images to Docker Hub**

```bash
docker push ashikahammad/my-backend:latest
docker push ashikahammad/my-frontend:latest
```

**Purpose:** Uploads images to Docker Hub.

---

##  Cleaning Up

### **16. Remove Stopped Containers**

```bash
docker rm $(docker ps -aq)
```

**Purpose:** Removes all stopped containers.

### **17. Remove Unused Docker Images**

```bash
docker image prune -a
```

**Purpose:** Deletes unused images to free up disk space.

### **18. Remove Docker Networks and Volumes**

```bash
docker network prune
docker volume prune
```

**Purpose:** Cleans up unused networks and volumes.

---

## 📌 Summary

This document outlines all necessary Docker commands used in the assignment, including:

- Building and running containers
- Using Docker Compose
- Debugging and monitoring
- Pushing images to Docker Hub
- Cleaning up Docker resources

This ensures a well-structured and efficient containerized development workflow. 

















