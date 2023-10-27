## 🐳 Docker Setup

This guide will walk you through the process of setting up a Docker environment and using it to build and manage containerized applications.

### Step 1: Creating a Dockerfile

Create a Dockerfile (usually named `Dockerfile`) in your project directory. The Dockerfile defines the instructions to create a Docker image.

```dockerfile
# Use an official base image
FROM ubuntu:latest

# Update package lists and install a program (e.g., curl)
RUN apt-get update && apt-get install -y curl

# Any other setup or configuration steps can go here

# Specify the command to run when the container starts
CMD ["/bin/bash"]
```

### Step 2: Building the Docker Image

Navigate to the directory containing your Dockerfile using the terminal. You can use the following commands to build the Docker image:

```bash
# Navigate to the directory containing your Dockerfile
cd /path/to/your/Dockerfile/directory

# Build the Docker image (name it hello-docker)
docker build -t hello-docker .
```

### Step 3: Listing Docker Images

You can list your Docker images with the following terminal command:

```bash
docker image ls
```

The `docker image ls` command will produce output similar to the following:

```markdown
REPOSITORY TAG IMAGE ID CREATED SIZE
hello-docker latest 9b854fe40a57 14 minutes ago 187MB
```

### Step 4: Pushing to Docker Hub

Pushing your Docker image to Docker Hub is a two-step process.

1. Tag your image with your Docker Hub repository and version:

```bash
docker tag hello-docker:latest <username>/<dockerhubreponame>:latest
```

2. Push the tagged image to Docker Hub:

```bash
docker push <username>/<dockerhubreponame>:latest
```

If your image is large, Docker will resume the push from where it left off, making the process efficient.

That's it! Your Docker image is now available on Docker Hub and can be pulled and used on other systems.
