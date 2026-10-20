DevOpsFlow — CI/CD Pipeline with GitHub Actions & Docker

> Elevate Labs Internship — Project 1



A production-style CI/CD pipeline for a containerized static web application using GitHub Actions, Docker, Docker Hub, and Docker Compose.

The project automatically validates the application, builds a Docker image, and pushes the image to Docker Hub whenever changes are pushed to the main branch.


---

📌 Project Overview

DevOpsFlow is a responsive DevOps-themed static web application created as part of the Elevate Labs internship.

The application is containerized using Docker and integrated with a GitHub Actions CI/CD pipeline.

CI/CD Flow

Developer
   │
   ▼
GitHub Repository
   │
   │ Push to main
   ▼
GitHub Actions
   │
   ├── Test
   │
   ├── Build Docker Image
   │
   └── Push Image
          │
          ▼
      Docker Hub
          │
          ▼
   Docker Pull / Run
          │
          ▼
   Local Application


---

🎯 Objectives

- Build a responsive static web application.
- Containerize the application using Docker.
- Run the application using Docker Compose.
- Create an automated CI/CD pipeline using GitHub Actions.
- Build a Docker image automatically.
- Push the image to Docker Hub automatically.
- Verify the Docker image locally.
- Follow basic DevOps and CI/CD practices.


---

🛠️ Tools & Technologies

Tool / Technology	Purpose

HTML5	Application structure
CSS3	Styling and responsive design
Docker	Application containerization
Docker Compose	Local container deployment
Nginx	Web server
Git	Version control
GitHub	Source code hosting
GitHub Actions	CI/CD automation
Docker Hub	Container image registry
Docker Desktop	Local Docker environment



---

📂 Project Structure

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


---

🌐 Application

The application is a responsive DevOps-themed dashboard called DevOpsFlow.

It is built using only:

- HTML
- CSS

No JavaScript or external application framework is required.


---

🐳 Docker Configuration

The application uses Nginx Alpine as the base image.

The Docker image:

1. Uses a lightweight Nginx Alpine image.
2. Copies index.html into the Nginx web directory.
3. Copies style.css into the Nginx web directory.
4. Exposes port 80.

The container listens on port 80.

For local development, the host exposes the application through port 8080.


---

🚀 Run Locally with Docker Compose

Make sure Docker Desktop is running.

1. Clone the repository

git clone https://github.com/nileshyadav2803/Elevate-Project-1-CICD.git

2. Enter the project directory

cd Elevate-Project-1-CICD

3. Build and start the container

docker compose up -d --build

4. Verify the running container

docker ps

5. Open the application

http://localhost:8080

6. Stop the application

docker compose down


---

⚙️ CI/CD Pipeline

The project uses GitHub Actions for continuous integration and continuous delivery.

Workflow file:

.github/workflows/ci-cd.yml

The workflow runs automatically when code is pushed to the main branch.

Pipeline Stages

1. Test

The workflow checks whether all required project files are available:

index.html
style.css
Dockerfile
docker-compose.yml

If the required files are missing, the workflow fails.


---

2. Build Docker Image

GitHub Actions builds the Docker image using Docker Buildx.

The build stage verifies that the Dockerfile can successfully create the application image.


---

3. Push Image to Docker Hub

After a successful build, GitHub Actions logs in to Docker Hub using repository secrets and pushes the image.

Docker image:

nileshyadavny/elevate-project-1-cicd:latest


---

🔐 GitHub Secrets

Docker Hub credentials are not stored directly inside the workflow file.

The following GitHub repository secrets are used:

DOCKERHUB_USERNAME
DOCKERHUB_TOKEN

This keeps the Docker Hub credentials protected while allowing GitHub Actions to authenticate securely.


---

🐋 Docker Hub Image

The Docker image is available on Docker Hub as:

nileshyadavny/elevate-project-1-cicd:latest

The latest tag represents the latest successfully pushed version of the application image.


---

🔄 CI/CD Process

Code Change
     │
     ▼
Git Push
     │
     ▼
GitHub
     │
     ▼
GitHub Actions
     │
     ▼
Validate Files
     │
     ▼
Build Docker Image
     │
     ▼
Docker Hub Login
     │
     ▼
Push Docker Image
     │
     ▼
Docker Hub

This removes the need to manually build and push the Docker image after every change.


---

🧪 Verification

The project was verified at multiple stages.

Local Application

The application was successfully opened through:

http://localhost:8080

Docker Container

The container was verified using:

docker ps

Docker Image

The local Docker image was verified using:

docker images

Docker Hub

The image was successfully pushed with the:

latest

tag.

GitHub Actions

The CI/CD workflow was successfully executed with all stages completed successfully.


---

📸 Project Evidence

Screenshots demonstrating the project execution and CI/CD pipeline can be added below.

Application Running

Screenshot:
Local application running on localhost:8080

Docker Container

Screenshot:
Docker container running successfully

Docker Image

Screenshot:
Docker image available locally

GitHub Actions

Screenshot:
Successful GitHub Actions CI/CD workflow

Docker Hub

Screenshot:
Docker Hub repository containing the latest image


---

💡 Key DevOps Concepts Demonstrated

<details>
<summary><strong>Click to view concepts</strong></summary>Containerization

Docker packages the application and its required web server environment into a portable container.

CI/CD

GitHub Actions automates validation, Docker image building, and image publishing.

Infrastructure Consistency

The Dockerfile defines a consistent environment for running the application.

Image Registry

Docker Hub acts as a centralized registry for storing and distributing the Docker image.

Automation

The pipeline reduces manual work by automatically building and publishing the image after code changes.

Version Control

Git and GitHub maintain the application's source code and project history.

</details>
---

🧠 What I Learned

<details>
<summary><strong>Click to view learning outcomes</strong></summary>- How to containerize a web application using Docker.
- How Dockerfiles define container images.
- How Docker Compose simplifies local deployment.
- How GitHub Actions automates CI/CD workflows.
- How Docker images are pushed to Docker Hub.
- How GitHub repository secrets protect credentials.
- How source code, CI/CD, and container registries work together.
- How to verify containers and Docker images locally.

</details>
---

▶️ Quick Start

For a quick local deployment:

git clone https://github.com/nileshyadav2803/Elevate-Project-1-CICD.git
cd Elevate-Project-1-CICD
docker compose up -d --build

Then open:

http://localhost:8080


---

🧹 Cleanup

To stop and remove the project containers:

docker compose down

To view running containers:

docker ps

To view Docker images:

docker images


---

## 📋 Project Checklist

- ✅ Responsive web application
- ✅ Dockerfile created
- ✅ Docker Compose configuration
- ✅ Local Docker deployment
- ✅ GitHub repository
- ✅ Git version control
- ✅ GitHub Actions workflow
- ✅ Automated Docker image build
- ✅ Docker Hub authentication
- ✅ Docker Hub image push
- ✅ CI/CD workflow verification
- ✅ Docker image verification

---

🏁 Conclusion

This project demonstrates a complete beginner-friendly CI/CD workflow for a containerized web application.

The application is developed using HTML and CSS, containerized using Docker, automatically built through GitHub Actions, and published to Docker Hub.

The project provides practical experience with essential DevOps concepts including Git, GitHub, Docker, Docker Compose, CI/CD automation, secrets management, and container registries.


---

👨‍💻 Author

Nilesh Yadav

BCA Fresher | Cloud & DevOps Learner

Project: Elevate Labs Internship — Project 1


---

⭐ Project Status

Status: Completed

Pipeline: GitHub Actions → Docker Build → Docker Hub

Deployment: Local Docker
