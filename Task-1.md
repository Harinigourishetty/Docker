# Docker Installation and Basic Commands

## 📘 Overview
This document explains how to **install Docker** on Ubuntu and the **commands executed** during the setup and image/container management process.  
The environment used was **Ubuntu Server**, and the hostname was set as **Docker-Lab**.

---

## ⚙️ Step 1: System Update

Before installing Docker, always update the package repository to ensure all packages are up-to-date.

```bash
sudo apt update -y
````
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/df30fe0a-2710-413a-b585-318b310d227d" />

---

## 🖥️ Step 2: Set Hostname

You can customize your hostname for identification purposes.

```bash
sudo hostnamectl set-hostname Docker-Lab
```
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/918150a9-0eca-4b85-a685-84bd7ea2f86f" />

After setting the hostname, reboot the system to apply the changes.

```bash
sudo init 6
```

---

## 🐋 Step 3: Check Docker Service Status

Verify whether Docker is installed and running properly:

```bash
sudo systemctl status docker
```
<img width="1917" height="620" alt="image" src="https://github.com/user-attachments/assets/a57a9183-40f3-4b91-b795-b5ac17ae6808" />

---

## 📦 Step 4: Pulling Docker Images

You can download images from **Docker Hub** using the `docker pull` command:

```bash
docker pull sonatype/nexus3
```
<img width="1506" height="332" alt="image" src="https://github.com/user-attachments/assets/96b5c615-323d-44bb-8546-53b0bb9dcc23" />

To check available images:

```bash
docker images
```
<img width="1378" height="110" alt="image" src="https://github.com/user-attachments/assets/cad1ffbe-4267-4d1f-a93d-af8fc2ed2e03" />

---

## 🚀 Step 5: Running Containers

Start a container from an image:

```bash
docker run sonatype/nexus3
docker run tomcat
docker run tomcat:tomcat9
docker run centos:centos8
```

To run a container in **interactive mode (with terminal access):**

```bash
docker run -it centos:centos8
```
<img width="1891" height="525" alt="image" src="https://github.com/user-attachments/assets/dc2b1eb8-197f-4c08-91ab-68e6f1f11657" />

To run a container in **detached mode (background):**

```bash
docker run -dt centos:centos8
```
<img width="1916" height="240" alt="image" src="https://github.com/user-attachments/assets/17d68a8d-2b43-4065-9e63-1fbe4b2ce683" />

---

## 📋 Step 6: Viewing Running and Stopped Containers

List running containers:

```bash
docker ps
```

List **all containers**, including stopped ones:

```bash
docker ps -a
```
<img width="1838" height="212" alt="image" src="https://github.com/user-attachments/assets/583f04c5-2c00-47b3-a0d2-8988f41626b7" />

Inspect a container’s configuration and metadata:

```bash
docker inspect <container_id>
```
<img width="1910" height="841" alt="image" src="https://github.com/user-attachments/assets/c017695a-832f-440d-bc6c-55d2eec755da" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/edb04780-02fd-4299-a5db-c327600af9b6" />

---

## 🛑 Step 7: Manage Containers

Stop a running container:

```bash
docker stop <container_id>
```
<img width="1835" height="267" alt="image" src="https://github.com/user-attachments/assets/fba0666a-6b25-4536-a096-8015652c28f6" />

Start a stopped container:

```bash
docker start <container_id>
```
<img width="1845" height="246" alt="image" src="https://github.com/user-attachments/assets/7f299c1a-7d4a-4608-b6eb-796e1813c589" />

Remove a specific container:

```bash
docker rm <container_id>
```
<img width="1879" height="63" alt="image" src="https://github.com/user-attachments/assets/6088378f-afec-4895-92be-ec891b86e15f" />

Remove multiple containers at once:

```bash
docker rm -f <container_id_1> <container_id_2> ...
```
<img width="889" height="58" alt="image" src="https://github.com/user-attachments/assets/c290067b-66d5-46e8-9310-0b22f8512689" />

---

## 🧹 Step 8: Manage and Clean Up Images

View available images:

```bash
docker images
```
<img width="1137" height="137" alt="image" src="https://github.com/user-attachments/assets/7896ad72-5c01-4f9a-9a63-7f293d88ca33" />

Remove a specific image:

```bash
docker rmi <image_id>
```
<img width="1268" height="478" alt="image" src="https://github.com/user-attachments/assets/ccfb2765-663e-40bc-993b-172f4d4fff4e" />

Force-remove an image:

```bash
docker rmi -f <image_id>
```

Remove all unused containers, networks, and images (cleanup):

```bash
docker image prune -a
```

---


---

## ✅ Summary of Key Commands

| Action                  | Command Example                            |
| ----------------------- | ------------------------------------------ |
| Update system           | `sudo apt update -y`                       |
| Set hostname            | `sudo hostnamectl set-hostname Docker-Lab` |
| Check Docker status     | `sudo systemctl status docker`             |
| Pull image              | `docker pull <image_name>`                 |
| Run container           | `docker run <image_name>`                  |
| List running containers | `docker ps`                                |
| List all containers     | `docker ps -a`                             |
| Stop container          | `docker stop <container_id>`               |
| Start container         | `docker start <container_id>`              |
| Remove container        | `docker rm <container_id>`                 |
| Remove image            | `docker rmi <image_id>`                    |
| Prune all               | `docker image prune -a`                          |


---

## 📘 Notes

* Always use `sudo` with Docker commands if you’re not part of the `docker` group.
* Use `docker ps -a` frequently to check the state of containers.
* Regularly prune unused containers and images to save disk space.

---

```
