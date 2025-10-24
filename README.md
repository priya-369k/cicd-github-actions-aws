# cicd-github-actions-aws
A production-ready CI/CD pipeline implementing GitOps principles using GitHub Actions for automated testing, building, and deployment to AWS ECS. This project demonstrates enterprise-grade DevOps practices with comprehensive code quality checks and zero-downtime deployments.

## 🚀 Features

- **Automated Testing**: Maven unit tests, Checkstyle validation, and SonarCloud analysis
- **Quality Gates**: Enforced code quality standards with configurable thresholds
- **Containerization**: Docker-based application packaging for consistency
- **Cloud Deployment**: Automated deployment to AWS ECS with rolling updates
- **Zero Downtime**: Health-check based traffic routing via Application Load Balancer
- **Security**: Secrets management through GitHub Secrets and AWS IAM
- **Traceability**: Git SHA-based image tagging for version control

## 🏗️ Architecture



**Key Components:**
- **GitHub Actions**: Workflow orchestration and CI/CD automation
- **Maven**: Build automation and dependency management
- **SonarCloud**: Code quality and security analysis
- **Docker**: Application containerization
- **AWS ECR**: Private container registry
- **AWS ECS**: Container orchestration service
- **AWS RDS**: Managed database service
- **Application Load Balancer**: Traffic distribution and health checks

## 📋 Prerequisites

### Required Tools
- Git (v2.30+)
- Java (JDK 11+)
- Maven (v3.6+)
- Docker (v20.10+)
- AWS CLI (v2.0+)

### Required Accounts
- GitHub account with repository access
- AWS account with appropriate permissions
- SonarCloud account (free for public repos)

### Required Permissions
- GitHub: Repository admin access
- AWS: ECS, ECR, RDS, ALB, IAM permissions
- SonarCloud: Project creation and token generation

## 🔄 CI/CD Workflow

The pipeline consists of three sequential jobs:

### **Job 1: Test**
- Checkout code from repository
- Run Maven unit tests (JUnit)
- Execute Checkstyle validation
- Perform SonarQube code analysis
- Evaluate SonarCloud quality gate

### **Job 2: Build**
- Checkout code
- Build Docker image with commit SHA tag
- Authenticate with AWS ECR
- Push image to container registry

### **Job 3: Deploy**
- Update ECS task definition with new image
- Register new task definition revision
- Deploy to ECS service with rolling update
- Health check verification via ALB
- Zero-downtime traffic transition

## 📊 Quality Standards

### Code Coverage
- Minimum: 80% line coverage
- Target: 90%+ coverage

### SonarCloud Metrics
- Security Rating: A
- Maintainability Rating: A or B
- Reliability Rating: A
- No blocker or critical issues

### Checkstyle Rules
- Maximum line length: 120 characters
- Proper indentation and formatting
- Complete Javadoc for public APIs
- No unused imports

