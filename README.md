# DevOps Quick Demo

A lightweight **DevOps CI pipeline** demonstrating containerization, automated testing, and GitHub Actions using a Python Flask application.

## 🚀 Project Overview

This project demonstrates a simple software delivery workflow from source code through automated validation and containerization.

The application is a small Flask API with health-check functionality. GitHub Actions automatically tests the application and builds a Docker image whenever changes are pushed to the repository.

### Architecture

```text
Developer
    │
    ▼
  Git
    │
    ▼
 GitHub
    │
    ▼
GitHub Actions
    │
    ├── Checkout
    ├── Python Setup
    ├── Install Dependencies
    ├── Run Pytest
    ├── Build Docker Image
    ├── Run Container
    └── Health Check
           │
           ▼
       Flask API
```

## 🛠️ Technologies

* **Python 3.12**
* **Flask**
* **pytest**
* **Docker**
* **Git / GitHub**
* **GitHub Actions**
* **Gunicorn**
* **Linux / WSL**

## 📁 Project Structure

```text
devops-quick-demo/
├── .github/
│   └── workflows/
│       └── ci.yml
├── app.py
├── test_app.py
├── requirements.txt
├── Dockerfile
└── .dockerignore
```

## 🔄 CI Pipeline

The GitHub Actions workflow automatically performs the following:

1. Checks out the source code.
2. Configures Python 3.12.
3. Installs application dependencies.
4. Executes automated tests with pytest.
5. Builds the Docker image.
6. Starts the container.
7. Performs an HTTP health check against `/health`.

A successful workflow provides automated validation that the application can be tested, containerized, and started successfully.

## 🧪 Application Endpoints

### Application

```text
GET /
```

Returns application status information.

### Health Check

```text
GET /health
```

Returns:

```json
{
  "status": "healthy"
}
```

## 🐳 Run Locally

Clone the repository:

```bash
git clone https://github.com/Maxeegit/devops-quick-demo.git
cd devops-quick-demo
```

Create a Python virtual environment:

```bash
python3 -m venv .venv
source .venv/bin/activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Run the tests:

```bash
pytest
```

Build the Docker image:

```bash
docker build -t devops-quick-demo:1.0 .
```

Run the container:

```bash
docker run -d \
  --name devops-quick-demo \
  -p 8001:8000 \
  devops-quick-demo:1.0
```

Test the application:

```bash
curl http://localhost:8001/health
```

## 🔐 DevOps Practices Demonstrated

* Source control with Git
* GitHub-based collaboration
* Automated CI
* Automated unit testing
* Docker containerization
* Containerized application deployment
* Health-check validation
* Infrastructure-independent application packaging
* Automated build verification

## 🎯 Project Objective

The objective of this project was to demonstrate the fundamentals of a modern DevOps workflow:

**Code → Test → Build → Containerize → Validate**

This project complements my larger AWS Cloud Security / DevSecOps project by demonstrating the core software delivery and automation practices used within modern engineering teams.

## 👤 Author

**Ayoola Bolarinwa**

Cloud Security | DevSecOps | GRC & Technology Risk

### Areas of Interest

AWS Cloud Security • DevSecOps • IAM • Infrastructure as Code • CI/CD • Container Security • Cloud Governance
