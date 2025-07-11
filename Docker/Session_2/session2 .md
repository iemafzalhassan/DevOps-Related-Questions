**Docker Session 1: Questions**

Welcome to Session 2 of our Docker learning series!

This session focused on "From Virtual Machine Struggles to Docker Magic" — giving everyone a practical understanding of how modern containerization is revolutionizing development.
Below are the questions discussed:

# 1. What is WSL and how does it help run Linux environments inside Windows?


# 2. What is Docker and why is it preferred over VMs for app deployment today?


# 3. What are the limitations of using WSL for production workloads?

 *Scenario-Based Questions*

Scenario Questions 1

**Docker Container Not Accessible**

Scenario:

You’ve deployed an NGINX container using the command:

```bash
docker run -d -p 8080:80 nginx
```

But when accessing http://localhost:8080, the browser shows "This site can’t be reached".

Question:
What steps would you take to troubleshoot this issue? Mention how networking works in Docker + WSL.

Scenario Questions 2

**Docker Installation Issues**

Scenario:

A teammate tries to install Docker Desktop but gets an error that Hyper-V is disabled, and Docker won’t start.

Question:

What would you check first? How can WSL2 resolve this issue, and what settings should be enabled during installation?
