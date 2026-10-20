# 🚀 DevOpsFlow — CI/CD Pipeline with GitHub Actions & Docker

### Elevate Labs Internship — Project 1

A responsive DevOps-themed static web application with an automated **CI/CD pipeline using GitHub Actions and Docker**. The project demonstrates containerization, automated validation, Docker image building, Docker Hub integration, and local deployment.

---

## 📌 Project Overview

**DevOpsFlow** is a responsive static web application created using **HTML and CSS** as part of the Elevate Labs internship.

The application is containerized using **Docker** and integrated with **GitHub Actions** to automate the CI/CD process.

Whenever changes are pushed to the `main` branch, GitHub Actions automatically:

* Validates the required project files
* Builds the Docker image
* Authenticates with Docker Hub
* Pushes the image to Docker Hub

The published Docker image can then be pulled and deployed locally.

---

## 🔄 CI/CD Pipeline

<details>
<summary><strong>🚀 Click to expand the complete CI/CD workflow</strong></summary>

### 1️⃣ Developer

Code is developed and tested locally.

⬇️

### 2️⃣ GitHub Repository

Changes are committed and pushed to the `main` branch.

⬇️

### 3️⃣ GitHub Actions

The automated CI/CD workflow starts.

**Validation Stage**

* Checkout repository
* Verify required project files
* Validate project structure

⬇️

**Docker Build Stage**

* Set up Docker Buildx
* Build Docker image using the `Dockerfile`

⬇️

**Docker Hub Stage**

* Authenticate securely using GitHub Secrets
* Build the final image
* Push the image to Docker Hub
* Tag the image as `latest`

⬇️

### 4️⃣ Local Deployment

The Docker image is pulled from Docker Hub and executed locally.

⬇️

### 5️⃣ Web Application

The DevOpsFlow application becomes available through the browser.

</details>

### 🧭 Quick Flow

```text
Developer
    ↓
GitHub Repository
    ↓
GitHub Actions
    ↓
Validate
    ↓
Build Docker Image
    ↓
Docker Hub
    ↓
Pull & Run Locally
    ↓
Web Application
```

---

## 🎯 Objectives

* Build a responsive static web application.
* Containerize the application using Docker.
* Create a Docker Compose configuration.
* Implement CI/CD using GitHub Actions.
* Automatically build a Docker image.
* Push the image to Docker Hub.
* Deploy and verify the application locally.
* Understand the complete CI/CD workflow.

---

## 🛠️ Tools & Technologies

| Technology     | Purpose                       |
| -------------- | ----------------------------- |
| HTML5          | Application structure         |
| CSS3           | Styling and responsive design |
| Git            | Version control               |
| GitHub         | Source code repository        |
| GitHub Actions | CI/CD automation              |
| Docker         | Application containerization  |
| Docker Compose | Local container management    |
| Docker Hub     | Container image registry      |
| Nginx Alpine   | Web server                    |
| VS Code        | Development environment       |

---

## 📁 Project Structure

```text
Elevate-Project-1-CICD/
│
├── .github/
│   └── workflows/
│       └── ci-cd.yml
│
├── Dockerfile
├── docker-compose.yml
├── index.html
├── style.css
└── README.md
```

---

## 🌐 Application

The application is a responsive DevOps-themed dashboard named **DevOpsFlow**.

It is built using only:

* HTML5
* CSS3

No JavaScript or external application framework is required.

The interface includes responsive sections, navigation, project information, technology information, and DevOps-focused content.

---

## 🐳 Docker Configuration

The application uses **Nginx Alpine** as the lightweight web server.

### Dockerfile

```dockerfile
FROM nginx:alpine

COPY index.html /usr/share/nginx/html/index.html
COPY style.css /usr/share/nginx/html/style.css

EXPOSE 80
```

### Why Nginx?

Nginx is used to serve the static HTML/CSS application efficiently inside the Docker container.

---

## 🧩 Docker Compose

The project also includes a `docker-compose.yml` file for easy local deployment.

```yaml
services:
  web:
    build: .
    container_name: devopsflow-app
    ports:
      - "8080:80"
```

The application is exposed at:

```text
http://localhost:8080
```

---

## ▶️ Run Locally with Docker Compose

Make sure Docker Desktop is running.

```bash
docker compose up -d --build
```

Check the running container:

```bash
docker ps
```

Open the application:

```text
http://localhost:8080
```

Stop the application:

```bash
docker compose down
```

---

## ⚙️ GitHub Actions CI/CD

The workflow is located at:

```text
.github/workflows/ci-cd.yml
```

The pipeline contains three main jobs:

### 🔹 Test Application

Validates that the required project files exist:

* `index.html`
* `style.css`
* `Dockerfile`
* `docker-compose.yml`

### 🔹 Build Docker Image

Builds the Docker image using Docker Buildx.

### 🔹 Push Image to Docker Hub

After a successful build on the `main` branch:

* Logs in to Docker Hub
* Builds the image
* Pushes the image
* Uses the `latest` tag

---

## 🔐 GitHub Secrets

Docker Hub credentials are stored securely using GitHub Repository Secrets.

```text
DOCKERHUB_USERNAME
DOCKERHUB_TOKEN
```

Sensitive credentials are **not stored directly inside the workflow file**.

---

## 🐋 Docker Hub Image

**Docker Hub Repository:**

`nileshyadavny/elevate-project-1-cicd`

**Image:**

```text
nileshyadavny/elevate-project-1-cicd:latest
```

The image is automatically pushed by the GitHub Actions pipeline.

---

## 📥 Pull Docker Image from Docker Hub

```bash
docker pull nileshyadavny/elevate-project-1-cicd:latest
```

Verify the image:

```bash
docker images
```

---

## 🚀 Run the Docker Hub Image Locally

```bash
docker run -d --name elevate-cicd-app -p 8081:80 nileshyadavny/elevate-project-1-cicd:latest
```

Verify the container:

```bash
docker ps
```

Open the deployed application:

```text
http://localhost:8081
```

This verifies that the image pushed to Docker Hub can be successfully pulled and deployed locally.

---

## 🔍 Verification

The project was verified at multiple stages:

### ✅ Application Verification

The static web application was successfully opened in a browser.

### ✅ Docker Verification

The application was successfully built and executed inside a Docker container.

### ✅ GitHub Verification

The source code and CI/CD workflow were successfully pushed to GitHub.

### ✅ GitHub Actions Verification

The CI/CD workflow completed successfully.

### ✅ Docker Hub Verification

The Docker image was successfully pushed to Docker Hub with the `latest` tag.

### ✅ Docker Hub Deployment Verification

The Docker Hub image was successfully pulled and deployed locally.

---

## 📸 Project Evidence

The project includes evidence for:

* Local web application
* Running Docker container
* Local Docker deployment
* Docker Hub image
* Docker image available locally
* Docker Hub image running as a container
* Docker Hub image deployed application
* Successful GitHub Actions workflow

---

## 📚 Key DevOps Concepts

<details>
<summary><strong>🐳 What is Docker?</strong></summary>

Docker packages an application and its required environment into a portable container.

This helps maintain consistency between development and deployment environments.

</details>

<details>
<summary><strong>🔄 What is CI/CD?</strong></summary>

**Continuous Integration (CI)** automatically validates and builds changes.

**Continuous Delivery/Deployment (CD)** automates the process of making application artifacts available for deployment.

In this project, GitHub Actions performs the automated CI/CD workflow.

</details>

<details>
<summary><strong>🐙 What is GitHub Actions?</strong></summary>

GitHub Actions is an automation platform integrated with GitHub repositories.

It is used here to automatically validate the project, build the Docker image, and push the image to Docker Hub.

</details>

<details>
<summary><strong>🐋 What is Docker Hub?</strong></summary>

Docker Hub is a container image registry used to store and distribute Docker images.

The CI/CD pipeline pushes the project image to Docker Hub so it can later be pulled and deployed.

</details>

<details>
<summary><strong>🔐 Why use GitHub Secrets?</strong></summary>

GitHub Secrets allow sensitive credentials such as Docker Hub authentication tokens to be stored securely instead of writing them directly inside the workflow.

</details>

---

## 🧠 Learning Outcomes

Through this project, the following practical skills were developed:

* Git and GitHub workflow
* Repository management
* Docker image creation
* Docker container management
* Docker Compose
* Nginx-based static application deployment
* GitHub Actions
* CI/CD pipeline implementation
* Docker Hub image management
* Secure credential handling with GitHub Secrets
* Local container deployment and verification

---

## ⚡ Quick Start

### Clone Repository

```bash
git clone https://github.com/nileshyadav2803/Elevate-Project-1-CICD.git
```

```bash
cd Elevate-Project-1-CICD
```

### Start Application

```bash
docker compose up -d --build
```

### Open

```text
http://localhost:8080
```

---

## 🧹 Cleanup

Stop the Docker Compose deployment:

```bash
docker compose down
```

Stop and remove the Docker Hub deployment:

```bash
docker stop elevate-cicd-app
docker rm elevate-cicd-app
```

---

## 📋 Project Checklist

* ✅ Responsive web application
* ✅ HTML/CSS implementation
* ✅ Dockerfile created
* ✅ Docker Compose configuration
* ✅ Local Docker deployment
* ✅ GitHub repository
* ✅ Git version control
* ✅ GitHub Actions workflow
* ✅ Automated project validation
* ✅ Automated Docker image build
* ✅ Docker Hub authentication
* ✅ Docker Hub image push
* ✅ CI/CD workflow verification
* ✅ Docker image verification
* ✅ Docker Hub image local deployment

---

## 🏁 Conclusion

This project demonstrates a complete practical CI/CD workflow for a containerized static web application.

The application is developed using HTML and CSS, containerized using Docker, automatically validated and built using GitHub Actions, and published to Docker Hub.

The Docker image was then pulled from Docker Hub and deployed locally, completing the development-to-deployment workflow.

---

## 👨‍💻 Author

**Nilesh Yadav**

BCA Fresher | Aspiring Cloud Support Engineer → DevOps Engineer

**GitHub:**
`https://github.com/nileshyadav2803`

**Project Repository:**
`https://github.com/nileshyadav2803/Elevate-Project-1-CICD`

---

## 📌 Project Information

| 📋 Details | 🔹 Information |
|---|---|
| **Project** | Elevate Labs Internship — Project 1 |
| **Project Type** | CI/CD Pipeline |
| **Application** | DevOpsFlow |
| **Frontend** | HTML5 + CSS3 |
| **CI/CD** | GitHub Actions |
| **Containerization** | Docker |
| **Web Server** | Nginx Alpine |
| **Container Registry** | Docker Hub |
| **Deployment** | Local Docker |
| **Cost** | ₹0 |
