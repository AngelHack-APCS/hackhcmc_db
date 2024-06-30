# AngelHack Hackhcmc - Team AIO_APCS1 Database Repo

## Introduction 

This repository contains the database schema and data for our application.

### Frontend
You can access our frontend server [here](https://github.com/AngelHack-APCS/hackhcmc_frontend)

### Database
You can access our backend server [here](https://github.com/AngelHack-APCS/hackhcmc_backend)

### AI
You can access our AI service [here](https://github.com/AngelHack-APCS/hackhcmc_ai)

## Prerequisites

Before you begin, ensure you have the following installed:

- Docker: [Install Docker](https://www.docker.com/get-started)

## Getting Started

To use this Docker image, follow these steps:

1. **Clone the Repository**
```bash
git clone <repository-url>
cd <repository-directory>
```

2. **Create an Environment File**
Create a file named `.env` in the root directory of the repository. Add your PostgreSQL configuration details in this file:
```text
POSTGRES_DB=mydatabase
POSTGRES_USER=postgres
POSTGRES_PASSWORD=mysecretpassword
```
3. **Build the Docker Image**

```bash
docker build -t my-postgres-image .
```

4. **Run the Docker Container**
Start a new container using the built image and the environment variables from the `.env` file:
```bash
docker run --name my-postgres-container -d -p 5432:5432 --env-file .env my-postgres-image
```
- --name my-postgres-container: Assigns a name to the running container.
- -d: Runs the container in detached mode (background).
- -p 5432:5432: Maps port 5432 on your host to port 5432 in the container.
- --env-file .env: Loads environment variables from the .env file.

5. **Verify and Connect**
Verify that the container is running:
```bash
docker ps
```

6. **Connect in Visual Studio Code**
   
Install the extension `SQLTools` and connect to PostgreSQL following the above configurations.

## Cleanup
To stop and remove the Docker container when you're done, use the following commands:
```bash
docker stop my-postgres-container
docker rm my-postgres-container
docker rmi my-postgres-image
```
