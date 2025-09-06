# Docker

# Introduction
Docker is an open-source containerization platform that allows applications to run in lightweight, portable containers. Unlike virtual machines, containers share the host OS kernel, making them faster and more efficient. Docker ensures consistency across development, testing, and production, solving the classic “It works on my machine” problem.

# Prerequisites
Before using Docker, you should be familiar with:-
  1) Operating system basics (Linux/Windows).
  2) Command-line usage.
  3) Networking concepts (ports, IPs).
  4) Software deployment workflows.

# Installation and Setup 
Docker supports only Linux, macOS, and Windows.

For Linux write the following commands in bash:-
  -sudo apt-get update
  -curl -fsSL https://get.docker.com -o get-docker.sh
  -sh get-docker.sh
  -docker --version
Also, add your user to the Docker group to run commands without sudo by follwoing step:-
  -sudo usermod -aG docker $USER

# Why Docker Exists
Traditionally, applications ran on dedicated servers (bare metal), wasting resources. Virtual machines improved utilization but were heavy since each VM included a full OS. Docker containers solved this by packaging only the app and its dependencies while sharing the host OS, making them faster, portable, and scalable.

# How To Use
Basic Commands:
-Pull an image: docker pull nginx
-Run a container: docker run -d -p 8080:80 nginx
-List containers: docker ps
-Stop container: docker stop <id>

To build custom image:- 
-FROM python:3.9
-WORKDIR /app
-COPY requirements.txt .
-RUN pip install -r requirements.txt
-COPY . .
-CMD ["python", "app.py"]

To Build and Run:-
-docker build -t myapp .
-docker run -p 5000:5000 myapp

# Real World Use Cases
-Microservices: Deploy independent services.
-DevOps: Consistent builds in CI/CD pipelines.
-Testing: Spin up temporary environments.
-Legacy apps: Containerize without major changes.
-Scalable apps: Used by Netflix, Spotify, PayPal.

# Brief History
-2008: Google introduced Linux Containers (LXC).
-2013: Docker was created by Solomon Hykes.
-2014+: Docker rapidly became the industry standard.
-Today: Containers are central to cloud-native computing with Kubernetes handling orchestration.

# Why Docker is Preferred
| Feature      | Virtual Machines | Docker  |
| ------------ | ---------------- | ------- |
| Startup      | Minutes          | Seconds |
| Size         | GBs              | MBs     |
| Resource Use | High             | Low     |
| Portability  | Limited          | High    |
While alternatives like Podman exist, Docker’s ecosystem, tooling, and community support make it the most widely adopted solution.

# My Suggestions
In practice, Docker reduces onboarding time, accelerates deployment, and ensures consistency across environments. It is the foundation of modern DevOps and microservices and a must-know for developers aiming for scalability and reliability.