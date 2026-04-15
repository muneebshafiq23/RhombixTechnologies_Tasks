# MERN Todo App – Dockerized

A full-stack **MERN (MongoDB, Express, React, Node.js)** Todo App fully containerized using **Docker** and **Docker Compose**.
This project demonstrates production-ready containerization with isolated services for frontend, backend, and database.

---

## Original Project

This project is originally by **Luis Fernando**.  
I have only **Dockerized it for learning and deployment purposes**.

---

## Features

* Fully containerized MERN application
* Separate Docker images for frontend & backend
* MongoDB running in its own container
* Clean Docker Compose workflow
* Non-root containers (secure)
* Lightweight backend with Node Alpine
* Optimized multi-stage frontend build

---

## Tech Stack

| Layer            | Technology                       |
| ---------------- | -------------------------------- |
| Frontend         | React + Vite / CRA (your choice) |
| Backend          | Node.js + Express                |
| Database         | MongoDB                          |
| Containerization | Docker & Docker Compose          |
| OS               | Alpine Linux (lightweight)       |

---

##  Project Structure

```
mern-todo-app/
 ├── backend/
 │   ├── models/
 │   ├── routes/
 │   ├── server.js
 │   ├── package.json
 │   ├── Dockerfile
 │   ├── .env  (Not included in GitHub)
 │
 ├── frontend/
 │   ├── src/
 │   ├── public/
 │   ├── Dockerfile
 │   ├── package.json
 │
 ├── docker-compose.yml
 └── README.md
```

---

## Environment Variables (Backend)

Create a `.env` file inside the **backend** folder:

```
PORT=5000
MONGO_URI=mongodb://mongo:27017/todo-db
JWT_SECRET=your-secret
```

**⚠️ Note:**
`.env` file is ignored by Git using `.gitignore`.

---

##  Running the App with Docker Compose

### 1️⃣ Build & Start All Services:

```
docker compose up -d --build
```

### 2️⃣ Stop Services:

```
docker compose down
```

### 3️⃣ View Logs:

```
docker compose logs -f backend
```

---

##  Access the App

| Service     | URL                                            |
| ----------- | ---------------------------------------------- |
| Frontend    | [http://localhost:8080](http://localhost:8080) |
| Backend API | [http://localhost:5000](http://localhost:5000) |
| MongoDB     | mongodb://mongo:27017                          |

---

## Docker Images Used

* **Frontend:** Custom React build → nginxinc/nginx-unprivileged:1.29.3-alpine-perl
* **Backend:** Node.js 20 Alpine 
* **MongoDB:** `mongo:6.0.6-jammy`

---

##  Security Best Practices

* `.env` never pushed to GitHub
* Non-root users enabled inside Docker
* Lightweight Alpine base images
* Secrets passed only via environment variables
* No database credentials hardcoded anywhere

---

##  Author

Made  by **[Muneeb Shafiq]**
Feel free to fork, star ⭐, and contribute!
