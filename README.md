# CloudOpsDeploy
Automating Cloud-Native Application Deployment with Ansible, Docker, Kubernetes and Jfrog

# Summary:
This exercise focuses on automating the deployment of a cloud-native application using Ansible, Docker, and Kubernetes. The goal is to set up a development environment, deploy JFrog Artifactory, prepare a Python Flask application, automate its deployment on Kubernetes, expose it using Ingress, and push Docker images to Artifactory. The process is streamlined using Ansible playbooks and roles, leveraging various Ansible modules for efficient automation.

# Installation of Docker and kind:

Ansible playbook setup.yml installs Docker and verifies its installation.
It downloads and installs kind for creating a local Kubernetes cluster.

# Deployment of JFrog Artifactory:

Kubernetes deployment and service YAML files for JFrog Artifactory are created and deployed using Ansible.
Persistent volume claims and ingress are included for data persistence and external access.

# Preparing the Python Flask Application:

A basic Flask application with an API endpoint is developed.
The Flask application is containerized using a Dockerfile, specifying Python environment setup, dependencies installation, and the command to run the app.

# Automated Kubernetes Flask Deployment:

Ansible automates the creation of Kubernetes deployment and service for the Flask application using the k8s module.
Kubernetes YAML files defining the deployment and service are applied using Ansible.

# Exposing Python Flask:

If not already present, an Ingress controller is deployed (e.g., nginx-ingress) using Ansible.
Ingress rules are defined to map external requests to the Flask service.
Ansible is used to deploy the Ingress controller and create Ingress resources for routing external traffic to the Flask service.

# Pushing Docker Image to Artifactory:

Docker login to Artifactory is automated using credentials stored securely in Ansible Vault.
The built Docker image is pushed to the configured Docker repository in JFrog Artifactory, including tagging and pushing tasks.
The docker_image module in Ansible is utilized to build the image from the Dockerfile.

# Creation of Ansible Role:

Finally, all tasks are encapsulated into an Ansible role for easy management and reuse.
This exercise showcases the power of Ansible automation in streamlining the deployment process of cloud-native applications, ensuring consistency, reliability, and scalability in development and testing environments.
