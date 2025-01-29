# A simple MERN stack application

### Create a network for the docker containers

`docker network create demo`

### Build the client
`cd mern/frontend`
`docker build -t mern-frontend` 

### Run the client
`docker run --name=frontend --network=demo -d -p 4173:4173 mern-frontend`

### Verify the client is running
#### Open your browser and type 
  `http://localhost:5173`

### Run the mongodb container
`docker run --network=demo --name mongodb -d -p 27017:27017 -v ~/opt/data:/data/db mongodb:latest`

### Build the server
`cd mern/backend`
`docker build -t mern-backend` 

### Run the server
`docker run --name=backend --network=demo -d -p 5050:5050 mern-backend`






# Using Docker Compose
`docker compose up -d`





![image](https://github.com/user-attachments/assets/64bab110-f304-486f-beb4-cb56e1205c89)


![image](https://github.com/user-attachments/assets/461442b4-39df-49ab-b5e7-de690c6e2f42)
