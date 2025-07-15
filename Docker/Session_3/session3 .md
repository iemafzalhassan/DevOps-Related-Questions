# Docker Learning Series: Session 3  
## Topic: Docker Images, Registries & Dockerfiles Demystified  

Welcome to my session in the Docker learning series! We covered the **fundamentals of Docker images**, how to work with registries, and best practices for writing Dockerfiles.  

---

## 📌 Key Topics Covered  
1. **Docker Images**  
   - What is a Docker image? (Read-only template with layers)  
   - Layer caching and build optimization  
   - Image lifecycle: Build → Store → Run → Update → Cleanup  

2. **Docker Hub & Private Registries**  
   - Pulling/pushing images to Docker Hub  
   - Introduction to private registries (AWS ECR, Azure ACR)  
   - Tagging and versioning best practices  

3. **Writing Single-Stage Dockerfiles**  
   - Structure of a `Dockerfile`  
   - Key instructions: `FROM`, `COPY`, `RUN`, `CMD`, `EXPOSE`  
   - `.dockerignore` and reducing image size  

---

## 💡 Discussion Questions  
1. **Why are Docker images split into layers?**  
   - How does layer caching speed up builds?  
2. **When would you use a private registry vs. Docker Hub?**  
3. **What's the purpose of `.dockerignore` in a Docker project?**  

---

## 🔍 Scenario-Based Exercises  

### Scenario 1: Broken Image Build  
**Problem:**  
You're building a Python app image, but the build fails with:  
```dockerfile
FROM python:3.9  
COPY requirements.txt .  
RUN pip install -r requirements.txt

##Task:

Diagnose why the build might fail

Fix the Dockerfile and document the steps

## Scenario 2: Docker Hub Push Rejected
Problem:
You try to push an image to Docker Hub but get:
denied: requested access to the resource is denied

Task:

Resolve the issue (Hint: docker login + correct tagging format)

Write the exact commands to tag/push successfully

## Your Assignment
- Dockerfile Lab

Create a Dockerfile for a simple Flask app (use [this example]([url](https://github.com/LondheShubham153/flask-app-ecs.git)))

Optimize it for layer caching

Registry Practice
- Push your image to Docker Hub with a version tag (v1.0)

Documentation
- Add your solution (code + screenshots) to Docker/session-[X]/ in this repo
- Submit a Pull Request!


