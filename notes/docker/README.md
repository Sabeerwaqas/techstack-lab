# 🚢 What is Docker? 

Docker is a tool that helps us build, share, and run applications in a consistent environment — no matter where the app is running or what operating system it’s on.

## 🧠 Why Do We Need Docker?

Imagine this:  
You’ve created a Node.js application that requires **Node.js version 16** and **MongoDB version 4**. Now, you want your teammate to run the same app on their computer.

Without Docker, your teammate would have to manually install those exact versions of Node.js and MongoDB. But they might end up installing newer versions by mistake — and suddenly, your app starts throwing errors or crashes. Why? Because the app was tested with different versions of the dependencies.

This leads to one of the most common phrases in software development:

> _“It works on my machine!”_

To avoid these kinds of issues, we use Docker.

Docker ensures your app runs **the same way** on every machine by packaging everything it needs — the code, dependencies, runtime, and configuration — into one neat and isolated unit called a **container**.

---

## 🧱 Key Docker Concepts

There are two main components in Docker:

### 1. Docker Image
- A Docker image is like a **blueprint** of your application.
- It includes everything your app needs to run (OS, libraries, code, etc.).
- Think of it like a **class** in programming — it doesn’t run on its own, but it defines what a running container should look like.

### 2. Docker Container
- A container is a **running instance** of an image.
- It's similar to an **object** in programming — created from a class (image).
- Containers are what actually use your system’s resources like CPU and memory.

---

## ⚙️ Docker Advantages

- **Portable**: Runs anywhere — your machine, a teammate's, or a cloud server.
- **Lightweight**: Uses fewer system resources than full virtual machines.
- **Consistent**: Same environment across development, testing, and production.

---

## 🖥️ How to Install Docker Desktop & Run It

Here’s how you can get Docker up and running on your system:

### ✅ Step 1: Download Docker Desktop
- Visit: [https://www.docker.com/products/docker-desktop/](https://www.docker.com/products/docker-desktop/)
- Click on **“Download for Windows”** or **“Download for macOS”** based on your system.

### ✅ Step 2: Install Docker Desktop
1. Open the downloaded installer file.
2. Follow the installation wizard.
3. Restart your system if prompted.

### ✅ Step 3: Verify Docker Installation
Open a terminal or command prompt and run:

```bash
docker --version
```
✅ Step 4: Run Your First Container

Run the following command to test Docker:

```
docker run hello-world
```

## 🧪 Common Docker Commands (with Simple Examples)

Here are some essential Docker commands with beginner-friendly examples:

### 📥 `docker pull IMAGE_NAME`
Downloads an image from Docker Hub.

```bash
docker pull hello-world
```
Downloads the hello-world image — used to verify Docker is working.

### 📸 `docker images`

Lists all Docker images stored on your system.

```bash
docker images
```
Shows all downloaded images like ```hello-world```, ```alpine```, etc.

### ▶️ ```docker run IMAGE_NAME```

Runs a container from an image.

```bash
docker run hello-world
```

Runs a basic container that prints a confirmation message.

### 🖥️ ```docker run -it IMAGE_NAME```

Runs a container in interactive mode (with terminal access).

```bash
docker run -it alpine
```
Launches the Alpine Linux image. Inside the container, you can try commands like ls, echo, apk add, etc.

### 🛑 ```docker stop CONTAINER_NAME or CONTAINER_ID```

Stops a running container.

```bash
docker stop amazing_bhaskara
```

Stops the container named ```amazing_bhaskara```.

### ▶️ ```docker start CONTAINER_NAME or CONTAINER_ID```

Starts an existing (stopped) container.

```docker start amazing_bhaskara```

### 📦 ```docker ps```

Lists all running containers.

```bash
docker ps
```

### 📦 ```docker ps -a```

Lists all containers (running and stopped).

```bash
docker ps -a
```

### 🗑️ ```docker rmi IMAGE_NAME```

Deletes an image from your system.

```bash
docker rmi hello-world
```

### 🗑️ ```docker rm CONTAINER_NAME```

Removes a container.

```bash
docker rm amazing_bhaskara
```

## 🔁 Summary Table (Beginner-Friendly)

| Command                      | Description                                     |
|-----------------------------|-------------------------------------------------|
| `docker pull hello-world`   | Download the test image                         |
| `docker run hello-world`    | Run a simple test container                     |
| `docker run -it alpine`     | Start Alpine in terminal mode                  |
| `docker ps`                 | List running containers                         |
| `docker ps -a`              | List all containers (including stopped ones)    |
| `docker stop <container>`   | Stop a container                                |
| `docker start <container>`  | Start a stopped container                       |
| `docker rm <container>`     | Remove a container                              |
| `docker rmi <image>`        | Remove an image                                 |
| `docker images`             | List all downloaded images                      |












