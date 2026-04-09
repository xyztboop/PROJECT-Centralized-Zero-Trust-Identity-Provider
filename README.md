# PROJECT-Centralized-Zero-Trust-Identity-Provider
Centralized Zero Trust Identity Provider (NexusAuth)

## Introduction
This project aims to develop a Centralized Identity and Access Management (IAM) system using modern Zero Trust principles. The system, named NexusAuth, is designed to provide secure authentication and authorization across multiple applications.
The primary objective of Week 1 was to set up the foundational infrastructure required for identity management using Keycloak and ensure successful access to the administrative interface.
________________________________________
## 2. Objective of Week 1
•	Install and configure Docker environment 

•	Deploy Keycloak IAM server

•	Verify server accessibility

•	Access Keycloak Admin Console

•	Create a dedicated project realm
________________________________________
## 3. Environment Setup

The project was implemented in a virtualized environment with the following configuration:

•	Operating System: Ubuntu (Virtual Machine)

•	Virtualization Tool: VirtualBox

•	Container Platform: Docker

•	IAM Tool: Keycloak

•	Host System: Windows
________________________________________
## 4. Docker Installation and Verification
Docker was installed on the Ubuntu virtual machine to enable containerized deployment of Keycloak.
Commands used:
***
sudo apt update
sudo apt install docker.io -y
***

Verification:
***
docker --version
***
Docker service was started and enabled successfully. This ensured that the system was ready to run containerized applications.





