# Mini-App

This is a simple Go application containerized with Docker and deployed to Kubernetes.

## Technologies Used

- Go
- Docker
- Kubernetes
- GitHub Actions

## Getting Started

### Local Development

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/Junnygram/mini-app.git
    cd mini-app
    ```
2.  **Run the application:**
    ```bash
    go run main.go
    ```

### Docker

1.  **Build the Docker image:**
    ```bash
    docker build -t mini-app .
    ```
2.  **Run the Docker container:**
    ```bash
    docker run -p 8080:8080 mini-app
    ```
    The application will be accessible at `http://localhost:8080`.

## Deployment

This application uses Kubernetes for deployment, with configurations for `dev`, `staging`, and `production` environments located in the `k8s/` directory. GitHub Actions workflows are set up to automate the build and deployment process.

## Project Structure

- `main.go`: The main Go application source code.
- `go.mod`: Go module definition.
- `Dockerfile`: Docker build instructions.
- `.github/workflows/`: GitHub Actions CI/CD workflows.
- `k8s/`: Kubernetes deployment manifests for different environments.
  - when pr merged to `dev/`: Development environment deployments, it rollouts and deploy dev namespace.
  - when pr merged to `staging/`: Development environment deployments, it rollouts and deploy dev namespace.
  - when pr merged to `production/`: Development environment deployments, it rollouts and deploy dev namespace.
