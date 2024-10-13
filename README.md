# Challenge

## Overview

This repository contains a simple web application with two main components:

1. **API**: Written in Laravel PHP, the API serves as the backend for the application and listens on port 8000.
2. **Client**: Developed using Nuxt.js, the client is the frontend of the application and listens on port 3000.

# UIconnect - Dockerized API & Client

This project contains an application made of two parts:
- **API** built with **PHP Laravel**.
- **Client** built with **Nuxt.js**.

### Project Objective:
- Create a Docker environment containing both API and Client.
- Use **MySQL** as the database for the API.
- Set up **Nginx** as a reverse proxy to forward requests between the Client and API.
- Add a **self-signed SSL certificate** to the Nginx server to enable HTTPS on port 443.

## Prerequisites

Before setting up the project, make sure you have the following tools installed:
- **Docker**
- **Docker Compose**

## Setup Steps:

### 1. Clone the Repository:
Clone the GitHub repository to your local machine using Git.

### 2. Build the Containers:
Use **Docker Compose** to build the containers for the application, including the containers for API, Client, Nginx, and MySQL.

### 3. Run the Containers:
Once the containers are built, run them using **Docker Compose**. MySQL will run on port 3306, API on port 8000, Client on port 3000, and Nginx will proxy requests over HTTPS on port 443.

### 4. Verify Nginx Configuration:
Ensure that Nginx is properly routing requests to both the Client and API. It should also work on HTTPS over port 443 using the self-signed SSL certificate.

## Configuration:

### 1. Dockerfile for **API (PHP Laravel)**:
The Dockerfile for the **PHP Laravel** API includes:
- Installation of PHP and required extensions like MySQL and GD.
- Installation of Composer to manage dependencies.
- Running the server on port 8000.

### 2. Dockerfile for **Client (Nuxt.js)**:
The Dockerfile for the **Nuxt.js** Client includes:
- Installation of Node.js and Nuxt dependencies.
- Building the application using Nuxt.
- Running the server on port 3000.

### 3. Docker Compose:
The **Docker Compose** file is set up to link various services such as:
- MySQL service (db)
- PHP Laravel API service (api)
- Nuxt.js Client service (client)
- Nginx service acting as a reverse proxy (nginx)

### 4. Self-Signed SSL Certificate:
A self-signed SSL certificate was created for the Nginx server to ensure secure HTTPS connections on port 443.

### 5. Nginx Configuration:
Nginx is configured to listen on port 443 (HTTPS) using the self-signed certificate, and it also proxies requests from the Client to the API.

## How to Run the Project
1. Open your terminal and navigate to the project directory where your docker-compose.yml is located.
2. Run the following command:
docker-compose up --build
This will:
Rebuild your Docker images (API, client, etc.).
Start all services (API, client, database, nginx).
Once it's finished, you'll be able to access your application, for example, through https://UIconnect.com if it's configured properly
   
## Notes:
- In case of issues, you can check the logs with the `docker-compose logs` command.

## Challenges:
- Ensuring that Nginx is properly routing requests.
- Enabling HTTPS with the self-signed certificate on Nginx.
- Managing all services centrally using Docker Compose.

- ![api_database](https://github.com/user-attachments/assets/a41cfee3-68b4-4dd3-8586-610c0440f1b9)




