📌 Task 1: Automate Code Deployment Using CI/CD Pipeline (GitHub Actions)
🎯 Objective:
To automate the process of building, testing, and deploying a Node.js application using GitHub Actions and Docker. This pipeline helps ensure that every code push is automatically tested, built, and deployed without manual intervention.

🧰 Tech Stack & Tools Used:
GitHub – Code repository and CI/CD trigger.

GitHub Actions – Automation tool for CI/CD.

Docker – Containerization of the application.

DockerHub – Image registry to push and store Docker images.

Node.js – Application framework.

🗂️ Project Structure:
pgsql
Copy
Edit
nodejs-demo-app/
│
├── .github/workflows/
│   └── docker-image.yml     <-- GitHub Actions workflow
├── Dockerfile               <-- Docker instructions
├── index.js                 <-- Node.js app entry
├── package.json             <-- App dependencies & scripts
🧠 What I Did Step-by-Step:
1. 📁 Cloned the Starter Repo
bash
Copy
Edit
git clone https://github.com/chandramah/TASK1.git
cd nodejs-demo-app
2. 🐳 Created a Dockerfile
Defined instructions to build the Node.js app into a Docker container.

3. 🔐 Added GitHub Secrets
Went to GitHub → Settings → Secrets and added:

DOCKER_USERNAME – My DockerHub username

DOCKER_PASSWORD – My DockerHub password or personal access token

4. ⚙️ Created CI/CD Workflow File
Path: .github/workflows/docker-image.yml

Pipeline Features:

Triggers on push to master

Logs into DockerHub

Builds Docker image

Pushes image to DockerHub

5. 🛠️ Git Commands Used
bash
Copy
Edit
git add .
git commit -m "Added GitHub Actions workflow"
git pull origin master --rebase   # To avoid conflicts
git push origin master
6. 🚀 Triggered the Pipeline
Pushed changes to GitHub → GitHub Actions automatically ran the pipeline → Docker image pushed to DockerHub successfully.

🔄 Workflow Summary
Stage	Tool Used	Description
Checkout	actions/checkout	Pulls repo code into the runner
Docker Login	docker/login-action	Authenticates DockerHub using secrets
Build	docker/build-push-action	Builds the image using Dockerfile
Push	Same as above	Pushes image to DockerHub

✅ Output:
Docker image successfully built and pushed to:
docker.io/19c51a0534/nodejs-demo-app:latest

GitHub Actions run completed with green check ✅
