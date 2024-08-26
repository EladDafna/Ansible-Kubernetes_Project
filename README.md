# Ansible-Kubernetes_Project

<img width="736" alt="Ansible_Diagrama_V1" src="https://github.com/user-attachments/assets/a4f7d652-bd90-439c-8f5e-06e81b7d01ac">



## Project Overview

🔹 **In this project, I created an automated environment for setting up a Kubernetes Cluster and web services using Ansible.** 🎯

This project demonstrates my capabilities in the DevOps field, showcasing my use of advanced tools such as Ansible, Docker, Kubernetes, Kind, HAProxy, and more.

🔹 **The goal was to set up a managed container infrastructure and ensure its proper functioning fully automatically.** 🚀

## Tools Used

- **Ansible** - Configuration management and automation tool. 🛠️
- **Docker** - Container environment setup. 🐳
- **Kubernetes (Kind)** - Container orchestration in a distributed environment. ☸️
- **Kubectl** - Management of the Kubernetes cluster. 📋
- **HAProxy** - Load balancing. ⚖️
- **Bash** - For running various script commands. 📜

## General Explanation of Each Role

### Role: Docker 🐳

Responsible for installing Docker and configuring the environment to be ready for container setup. This role includes installing all necessary dependencies, installing Docker, adding the user to the Docker group, and starting the Docker service.

### Role: Cluster_Kind ☸️

This role handles the installation of Kubernetes management tools (`kubectl`) and Kind for creating a local Kubernetes Cluster. It performs the necessary installations, creates the cluster with Kind, and ensures the `kubeconfig` configuration is updated.

### Role: Kubernetes 📦

Responsible for setting up resources in the created Kubernetes Cluster. This role includes applying a ConfigMap, deploying Nginx, and setting up a Service to expose the application on the network.

### Role: Check_Health ✅

This role is designed to check the health of the Pods in the created cluster. It checks if the Nginx Pods are in the 'Running' state and provides debugging information in case of failure.

### Role: Configure_Load_Balancer ⚖️

The purpose of this role is to install and configure HAProxy as a load balancer for services running in the Kubernetes Cluster. It installs HAProxy, updates its configuration file, and ensures the service is running correctly.

## Installation Instructions

To set up this project on your local machine, follow these steps:

1. **Clone the Repository**: 
   ```bash
   git clone https://github.com/EladDafna/Ansible-Kubernetes_Project.git
   cd Ansible-Kubernetes_Project
   ```

2. **Install Ansible**: 
   - Install Ansible following [the official documentation](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html).

3. **Run the Playbooks**:
   - Ensure you have Ansible installed and configured properly.
   - Run the main playbook to set up the environment:
     ```bash
     ansible-playbook -i inventory main.yml
     ```

   **Note:** All other tools, including Docker, Kubernetes, Kind, Kubectl, and HAProxy, will be automatically installed by the Ansible roles.

4. **Check the Deployment**:
   - Use `kubectl` to check the status of the Kubernetes cluster and deployed resources.
   - For example, to check all pods:
     ```bash
     kubectl get pods --all-namespaces
     ```

5. **Test Load Balancing**:
   - Verify that HAProxy is properly set up and that load balancing is functioning by accessing the service endpoint.

## Summary

This project demonstrates the ability to manage complex environments automatically using modern tools and highlights the importance of automation in the DevOps world. 🛠️

With Ansible, I successfully created an automated process that sets up an entire environment, including a Kubernetes Cluster and web services, within minutes, including health checks and load balancing. 🌐

This project is part of my ongoing learning and development in the field, and I plan to continue deepening my knowledge of additional tools and technologies in the future. 📈

