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

<img width="940" height="272" alt="image" src="https://github.com/user-attachments/assets/fea1d5f3-b426-44a2-8b65-ba10e4577217" />
 ________________________________________

## 5. Deployment of Keycloak Server

Keycloak was deployed using Docker in development mode.
Command used:
***
sudo docker run -p 8080:8080 \
-e KC_BOOTSTRAP_ADMIN_USERNAME=admin \
-e KC_BOOTSTRAP_ADMIN_PASSWORD=admin \
quay.io/keycloak/keycloak:latest \
start-dev --http-host=0.0.0.0
***
The server logs confirmed successful startup with the message:
***
Listening on: http://0.0.0.0:8080
***
<img width="902" height="271" alt="image" src="https://github.com/user-attachments/assets/4f41f1b8-510e-4a4c-a1d5-25fc00994b5d" />
________________________________________

## 6. Connectivity Verification
Initial browser access attempts resulted in connection issues due to VM networking limitations. 

This was resolved by:
•	Verifying container status using Docker commands

•	Testing server response using:
***
curl http://localhost:8080
***
The server responded with HTTP status and redirect headers, confirming that Keycloak was running correctly
<img width="940" height="409" alt="image" src="https://github.com/user-attachments/assets/207d0efc-3536-4562-80fb-d93cca541693" />
________________________________________

## 7. Accessing Keycloak Admin Console
The Keycloak Admin Console was successfully accessed using:
***
http://localhost:8080/admin/
***

Login credentials:
•	Username: admin
•	Password: admin

Successful login confirmed that the IAM system was operational.
 
 <img width="940" height="311" alt="image" src="https://github.com/user-attachments/assets/688d2c25-0391-481b-83ef-1f0a89cd24c7" />

 <img width="940" height="296" alt="image" src="https://github.com/user-attachments/assets/d9a45227-1de4-43ed-8cde-33a4da1b8d83" />
________________________________________

## 8. Realm Creation

A new realm was created to represent the project environment.

•	Realm Name: nexus-auth

The realm acts as an isolated environment for managing users, roles, and applications within the IAM system.

<img width="940" height="310" alt="image" src="https://github.com/user-attachments/assets/302f85ee-ec90-4041-a639-d9a563a3acde" />

<img width="940" height="310" alt="image" src="https://github.com/user-attachments/assets/f9dbf4ba-041c-450a-99a1-63fc277f8388" />

Create new user:

<img width="940" height="271" alt="image" src="https://github.com/user-attachments/assets/5233b407-42da-4cd4-8ae8-8334b908d9c5" />

<img width="940" height="367" alt="image" src="https://github.com/user-attachments/assets/208215a7-0e47-4114-87b8-6b8f58302112" />

Set credentials:

<img width="940" height="310" alt="image" src="https://github.com/user-attachments/assets/0d0dce86-e5e6-45a6-9b0b-8fd44a9105c7" />

<img width="940" height="427" alt="image" src="https://github.com/user-attachments/assets/2e97f2ae-cdcc-46d3-817a-1e68cab33aa8" />
________________________________________


## 9. Outcome of Week 1
By the end of Week 1, the following milestones were achieved:
•	Docker environment successfully configured
•	Keycloak server deployed and running
•	Admin console accessed successfully
•	Project-specific realm created
This establishes a strong foundation for implementing authentication, authorization, and security policies in subsequent weeks.
________________________________________


## 10. Conclusion
Week 1 focused on setting up the core infrastructure required for the IAM system. Despite initial networking challenges, the system was successfully deployed and accessed. The creation of the project realm marks the beginning of actual IAM configuration.
Future work will involve user management, role-based access control (RBAC), and application integration.
________________________________________
                           Week 2 (Application Integration + RBAC) 
________________________________________


## 1.	Create role: admin

-	A new role named “admin” was created in the nexus-auth realm using Keycloak.
This role defines administrative privileges within the system.
It will be used to control access and assign permissions to users.
The role was successfully created and is ready for assignment.

<img width="940" height="302" alt="image" src="https://github.com/user-attachments/assets/48f1aa0c-ad76-4b2c-ad77-edc10f56c2a6" />
________________________________________


## 2.	Role Assignment
The admin role was assigned to the user testuser in the nexus-auth realm.
This enables the user to have administrative privileges within the system.
Role assignment ensures proper access control based on user responsibilities.
The role mapping was successfully completed.

<img width="940" height="431" alt="image" src="https://github.com/user-attachments/assets/c0c7bd43-cf30-4c45-835c-fe784a4153f7" />

<img width="940" height="513" alt="image" src="https://github.com/user-attachments/assets/9954bf49-8817-4872-954c-a5fb75bf6836" /> 
________________________________________



 ## 3. Access Token Generation

An access token was generated for the user testuser using Keycloak.
The token contains user identity and role-related information in JSON format.
It is used for authentication and authorization in secured applications.
This confirms successful integration of role-based access control.

<img width="940" height="528" alt="image" src="https://github.com/user-attachments/assets/eb04133f-79eb-4ca4-bb99-49fdb16623df" />
________________________________________


## 4. Role Verification in Token:

The access token generated for testuser was analyzed to verify role assignment.
The admin role was successfully found within the token under realm_access.
This confirms that role-based access control (RBAC) is properly implemented.
The system can now enforce permissions based on assigned roles.

<img width="705" height="683" alt="image" src="https://github.com/user-attachments/assets/9648f9cd-e8a7-4e02-83f0-f4d3b5a87251" /> 
________________________________________


## 5. Client Configuration

A client named flask-app was created in the nexus-auth realm.
The redirect URI was configured to allow authentication via localhost.
Web origins were set to allow all requests during development.
This enables secure communication between the application and Keycloak.

<img width="940" height="483" alt="image" src="https://github.com/user-attachments/assets/7ee9c8b2-82d7-43ee-ab9f-d0d63e593d94" />
________________________________________


## 6. Flask Application Setup
A basic Flask application was successfully created and executed.
The application runs on localhost port 5000 and serves as a test interface.
This confirms that the development environment is properly configured.
It will be used to integrate Keycloak authentication (SSO).

<img width="940" height="614" alt="image" src="https://github.com/user-attachments/assets/5ac263c1-931c-46ea-b6c9-c70456200ca0" />

<img width="940" height="199" alt="image" src="https://github.com/user-attachments/assets/a1c2ffd2-5ef3-4bc2-94fe-e71b50dcc4d9" />

<img width="860" height="432" alt="image" src="https://github.com/user-attachments/assets/63df0b90-79e8-496a-a71c-3d0d8fee751d" />

<img width="940" height="329" alt="image" src="https://github.com/user-attachments/assets/4f8a6a61-1b17-4d53-abf1-6a030c58dd21" />

<img width="940" height="330" alt="image" src="https://github.com/user-attachments/assets/ef41a15e-f6ca-46bf-ac5a-412e736c1e4c" />

<img width="940" height="304" alt="image" src="https://github.com/user-attachments/assets/a0756bdd-d06a-4c79-bda6-224eb0509951" />

<img width="940" height="415" alt="image" src="https://github.com/user-attachments/assets/02f7fa06-1753-4688-8fbe-df99ddc62900" />

<img width="940" height="491" alt="image" src="https://github.com/user-attachments/assets/745e52d1-89c7-4f02-930c-1624be0f9970" />

Application intergration completed.
________________________________________
                                   WEEK 3: MFA + SECURITY HARDENING
________________________________________


## 1 Multi-Factor Authentication (OTP Setup):
  Multi-Factor Authentication (MFA) was implemented using OTP in Keycloak.
The user was required to configure OTP during login using an authenticator app.
A QR code was scanned to generate time-based one-time passwords.
This enhances security by adding a second layer of authentication.

<img width="940" height="464" alt="image" src="https://github.com/user-attachments/assets/93e14ecc-fcd5-4fce-a1e8-881f2b9512d1" />

<img width="940" height="463" alt="image" src="https://github.com/user-attachments/assets/113b1d5f-a942-418f-b3b2-473ec3440aa5" />

<img width="940" height="195" alt="image" src="https://github.com/user-attachments/assets/df88cb58-5968-4acb-a15a-9f7eb1276792" />
________________________________________


## 2.Brute Force Protection:
Brute force detection was enabled in Keycloak to prevent unauthorized access.
The system temporarily locks user accounts after multiple failed login attempts.
This helps protect against password guessing attacks.
It enhances overall system security and user account protection.

<img width="940" height="479" alt="image" src="https://github.com/user-attachments/assets/8c88d128-c2a8-480d-a95a-a44526e69e17" />

<img width="940" height="599" alt="image" src="https://github.com/user-attachments/assets/d5f7d073-e24e-48d8-a784-37410d4f0c44" /> 
________________________________________


## Security Hardening:

Security features such as multi-factor authentication (OTP), brute force protection, and password policies were implemented.
OTP ensures an additional layer of authentication using authenticator apps.
Brute force detection prevents repeated unauthorized login attempts.
Strong password policies enforce secure credential creation.

<img width="940" height="530" alt="image" src="https://github.com/user-attachments/assets/6e8919f6-f3e1-4573-a22f-359f9eb62b89" />
________________________________________
                                   WEEk4: LOGGING + FINAL TOUCHES                                 
________________________________________


## Objective:
 1. Enable Event Logging
•	Track login/logout 
•	Track failures 
________________________________________
🧾 2. Session Control
•	Set token expiry 
•	Secure sessions 
________________________________________
🎨 3. UI Branding (optional)
•	Change login theme 
• Make it look custom 
________________________________________


## 1.Event Logging and Monitoring
Event logging was enabled in Keycloak to track user activities.
User events such as login, logout, and authentication errors are recorded.
This helps in monitoring system usage and detecting suspicious activities.
It enhances auditing and security analysis capabilities.

<img width="940" height="469" alt="image" src="https://github.com/user-attachments/assets/15836490-d4bd-48a1-90f9-18bd6ae9a5cc" />

<img width="940" height="413" alt="image" src="https://github.com/user-attachments/assets/52510d9b-3b6d-4916-bb23-3113e0a24ed9" />

<img width="940" height="359" alt="image" src="https://github.com/user-attachments/assets/87ec6ab3-b857-4dc4-b283-425cf9500822" />

<img width="940" height="318" alt="image" src="https://github.com/user-attachments/assets/5f7dbb17-0402-4c06-9c4c-d3a055531e6f" />
________________________________________


## Conclusion
The project successfully demonstrated the implementation of an Identity and Access Management (IAM) system using Keycloak.
It covered user authentication, role-based access control, and secure application integration.
Advanced security features such as multi-factor authentication, brute force protection, and password policies were implemented.
Event logging and monitoring ensured proper tracking of user activities, making the system secure and reliable.
________________________________________


## Skills Gained
•	Understanding of Identity and Access Management (IAM) concepts 
•	Hands-on experience with Keycloak configuration and administration 
•	Implementation of Role-Based Access Control (RBAC) 
•	Integration of Single Sign-On (SSO) with a Flask application 
•	Implementation of Multi-Factor Authentication (OTP) 
•	Knowledge of security features like brute force protection and password policies 
________________________________________




