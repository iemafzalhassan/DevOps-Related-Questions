# Docker Learning Series: Session 2

### Topic: From Virtual Machine Struggles to Docker Magic

Welcome to **Session 2** of our Docker learning series!

This session provided a practical understanding of how containerization — especially using Docker — simplifies development and deployment compared to traditional virtual machines.

---

##  Discussion Questions

### 1. What is WSL and how does it help run Linux environments inside Windows?

---

### 2. What is Docker and why is it preferred over VMs for app deployment today?

---

### 3. What are the limitations of using WSL for production workloads?

---

##  Scenario-Based Questions

###  Scenario 1: Docker Container Not Accessible

**Scenario:**

You’ve deployed an NGINX container using the command:

```bash
docker run -d -p 8080:80 nginx
```

But when accessing http://localhost:8080, the browser shows "This site can’t be reached".

Question:
What steps would you take to troubleshoot this issue? Mention how networking works in Docker + WSL.


###  Scenario 2: Docker Installation Issues

**Scenario:**

A teammate tries to install Docker Desktop but gets an error that Hyper-V is disabled, and Docker won’t start.

Question:

What would you check first? How can WSL2 resolve this issue, and what settings should be enabled during installation?



###  What You Need to Do:

- Recreate each scenario on your own system.
- Troubleshoot and resolve the issue using the hints provided.
- Take **screenshots** of your process and results (e.g., Docker commands, browser results, WSL settings).
- Add your solution (step-by-step explanation + images) to this repository in the `Docker/session-2` folder.
- Raise a **Pull Request**
