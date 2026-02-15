# Inventory Management System MERN CRUD App

A simple MERN project that lets the user insert, update, delete & get products from the MongoDB.

## To Run App:

### 1. Open the folder in vs code and run (npm install) command.
   
### 2. In MongoDB Compass:
   - Create Database: IMS
   - Collection Name: products

### 3. Then in vs code, open two terminals in split:
   ![image](https://github.com/mhy20401/Inventory-Management-System-MERN-CRUD-Project/assets/99351091/86ed0828-84b8-43b0-89fd-8caa17b88833)

### 4. In one terminal run these commands (For Backend / Server):
   - cd Backend
   - npm run server

### 5. In the other terminal run these commands (For Frontend / Client):
   - cd Frontend
   - cd inventory_management_system
   - npm start
   ![image](https://github.com/mhy20401/Inventory-Management-System-MERN-CRUD-Project/assets/99351091/93fa528b-bc88-49c2-9922-19b317336b7c)

## Output:
### 1. GET (Displaying products)
   ![image](https://github.com/mhy20401/Inventory-Management-System-MERN-CRUD-Project/assets/99351091/09f7d43a-344b-4122-b415-b3736307cf45)

### 2. POST (Inserting a new product)
   ![image](https://github.com/mhy20401/Inventory-Management-System-MERN-CRUD-Project/assets/99351091/d31e9f36-c119-4a04-9cc0-ddc9fe94b159)
   ![image](https://github.com/mhy20401/Inventory-Management-System-MERN-CRUD-Project/assets/99351091/39ec387f-5efc-4c1f-a7eb-a87612acc17a)
   ![image](https://github.com/mhy20401/Inventory-Management-System-MERN-CRUD-Project/assets/99351091/a6b5c6bf-77d7-41ab-9ca0-3a8bfc71954d)
   ![image](https://github.com/mhy20401/Inventory-Management-System-MERN-CRUD-Project/assets/99351091/3d43e877-c2e6-414b-bef9-410caae1668e)

### 3. PUT (Updating a product)
   ![image](https://github.com/mhy20401/Inventory-Management-System-MERN-CRUD-Project/assets/99351091/d35f7ab0-3fda-4b1c-9055-67ca8c7b2ab6)
   ![image](https://github.com/mhy20401/Inventory-Management-System-MERN-CRUD-Project/assets/99351091/7dd107db-6fde-416d-b5c6-2175916f872f)

### 4. DELETE (Deleting a product)
   ![image](https://github.com/mhy20401/Inventory-Management-System-MERN-CRUD-Project/assets/99351091/d846ff43-6abd-4baa-9ed6-df736f2d411e)
   ![image](https://github.com/mhy20401/Inventory-Management-System-MERN-CRUD-Project/assets/99351091/cc6368bd-f391-4d6b-b814-c931d48a0878)

## EXTENSION 

# 📦 Containerized MERN Inventory Management System

This project demonstrates containerization and deployment of an existing MERN-based Inventory Management application using Docker and Docker Compose.

The focus of this project is on DevOps practices including:
- Writing Dockerfiles
- Managing containers manually
- Configuring networks and volumes
- Orchestrating services with Docker Compose

---

## 🛠️ Tech Stack

- Containerization: Docker
- Orchestration: Docker Compose

---

## 🐳 Manual Docker Setup (Before Docker Compose)

### Frontend

Build image:

    docker build -t frontend .

Run container:

    docker run -p 3000:3000 frontend

### Backend

Build image:

     docker build -t backend .

Run container:

      docker run -p 3001:3001 backend

MongoDB

  docker run -d \
  --name mongodb \
  --network network-name \
  -p 27017:27017 \
  -v mongo_data:/data/db \
  mongo

🌐 Networking

A custom Docker network was created to allow communication between:

  Frontend
  Backend
  MongoDB

Containers communicate using service/container names instead of localhost.

🐳 Docker Compose Implementation

Instead of running multiple docker build and docker run commands manually, Docker Compose was introduced.

Run all services using:

      docker-compose up --build

This:
      Builds images automatically
      Creates network automatically
      Starts all containers
      Manages dependencies

🔎 Access MongoDB Inside Container

To access MongoDB shell:
    docker exec -it inventory-management-system-mern-crud-app-mongodb-1 mongosh
Inside mongosh:

      show dbs
      use <collectionname>
      show collections


😄 Fun Fact

Initially, running separate Dockerfiles made my images a bit bulky.

After implementing multi-stage builds, my Docker image finally went on a diet 🐳💪 — smaller and cleaner.


---

# ✅ 4️⃣ Manual Docker vs Docker Compose 

### 🔹 Before Docker Compose

You had to:

- Build frontend image
- Run frontend container
- Build backend image
- Run backend container
- Start MongoDB separately
- Create network manually
- Attach containers to network

Too many steps ❌  
Easy to make mistakes ❌  

---

### 🔹 After Docker Compose

You only run:

     docker-compose up
