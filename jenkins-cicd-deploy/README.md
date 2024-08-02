# Prerequisite
Jenkins Plugins: Ensure that Jenkins has the necessary plugins:
Git Plugin for SCM integration.
SonarQube Scanner Plugin for code analysis.
Docker Pipeline Plugin for Docker operations.
AWS Steps Plugin for AWS CLI interactions.
Trivy installed on Jenkins nodes for container scanning.

Credentials:
SonarQube: Configure SonarQube credentials in Jenkins.
AWS: Configure AWS credentials in Jenkins for CLI access

Kubernetes Deployment: Ensure you have a Kubernetes deployment named my-app-deployment with a container named my-app-container in your EKS cluster.

Selenium Tests: The mvn test command assumes that Selenium tests are integrated with Maven. Adjust if Selenium tests are executed differently.

Dockerfile: Ensure that the Dockerfile is in the root of your repository or adjust the path as necessary.

# Environment Variables
AWS_REGION: Region where EKS is located.
EKS_CLUSTER_NAME: Name of the EKS cluster.
IMAGE_NAME: Name of the Docker image.
IMAGE_TAG: Tag for the Docker image.
DOCKERFILE_PATH: Path to the Dockerfile.
SONARQUBE_URL: URL of the SonarQube server.
SONARQUBE_PROJECT_KEY: SonarQube project key.
SONARQUBE_CREDENTIALS_ID: Jenkins credentials ID for SonarQube.
AWS_CREDENTIALS_ID: Jenkins credentials ID for AWS.

Stages:
Checkout SCM: Checks out code from AWS CodeCommit.
Code Scanning: Runs SonarQube analysis on the code.
Security Scan: Scans the Docker image with Trivy for vulnerabilities.
Testing: Runs Selenium tests. Make sure Selenium tests are integrated with Maven or adapt the command accordingly.
Build: Builds the Java application using Maven.
Docker Build: Builds the Docker image using the Dockerfile.
Deploy: Updates the Kubernetes deployment with the new Docker image.

# How to Run the Playbook:
Save the Jenkinsfile in your repository.

Configure a Jenkins Pipeline job to use this Jenkinsfile.

Make sure Jenkins has the required plugins and credentials set up.

Trigger the pipeline job and monitor the progress and results through Jenkins.