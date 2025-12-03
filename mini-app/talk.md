# How to Get Everything Working

This document outlines the steps to get your CI/CD pipeline up and running for the mini-app project.

### 1. Create a GitHub Repository

1.  Go to [https://github.com/new](https://github.com/new).
2.  Name your repository `mini-app-<your-name>`.
3.  Choose "Public" or "Private".
4.  Do **not** initialize the repository with a README, .gitignore, or license.
5.  Click "Create repository".

### 2. Push Your Code to the Repository

In your project directory (`student-ci-challenge-junior`), run the following commands in your terminal:

```bash
# Initialize a new Git repository if you haven't already
git init -b main

# Add the remote repository you just created on GitHub
git remote add origin https://github.com/<your-username>/<your-repo-name>.git

# Add all your files to the staging area
git add .

# Commit your files
git commit -m "Initial commit"

# Push your code to the main branch on GitHub
git push -u origin main
```

### 3. Create the Feature Branch

Create the feature branch as required by the assignment and push it to GitHub:

```bash
git checkout -b feature/-ci-setup
git push origin feature/-ci-setup
```

### 4. Add Secrets to Your GitHub Repository

Your CI/CD pipeline needs to log in to Docker Hub to push the container image. To do this securely, you need to add your Docker Hub username and password as secrets to your GitHub repository.

1.  Go to your repository on GitHub.
2.  Click on "Settings" > "Secrets and variables" > "Actions".
3.  Click "New repository secret".
4.  For the name, enter `DOCKER_USERNAME`.
5.  For the secret, enter your Docker Hub username.
6.  Click "Add secret".
7.  Repeat the process to add another secret named `DOCKER_PASSWORD` with your Docker Hub password or an access token.

# Assignment Submission

Here is what you need to submit for your assignment.

### 1. Repo Link

The URL of your GitHub repository.

Example: `https://github.com/<your-username>/mini-app-<your-name>`

### 2. Functional CI Pipeline + Screenshot

After you create a pull request (see step 5), the CI pipeline will automatically run.

1.  Go to the "Actions" tab in your GitHub repository to see the pipeline running.
2.  Take a screenshot of the successful pipeline run.

### 3. Dockerfile

The `Dockerfile` is already in your project directory.

### 4. Container Registry URL

The URL of the Docker image that was pushed to Docker Hub.

Example: `https://hub.docker.com/r/<your-docker-username>/mini-app`

### 5. Pull Request

1.  Go to the "Pull requests" tab in your GitHub repository.
2.  Click "New pull request".
3.  Set the "base" branch to `main` and the "compare" branch to `feature/-ci-setup`.
4.  Click "Create pull request".

### 6. Deployment Manifest

The `k8s-deployment.yaml` file is already in your project directory.
