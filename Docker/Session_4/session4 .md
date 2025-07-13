# Session 4: Container Management and Operations
______________________________________________________________________

## Aim

The aim of this session is to help learners understand and apply container management techniques using Docker. This includes writing efficient multi-stage Dockerfiles, managing containers with core CLI commands, troubleshooting issues, and preparing containers for development and testing workflows.


## Outcome

By the end of this session, learners will be able to:

- Create and understand multi-stage Dockerfiles for Java-based applications.
- Use essential Docker commands such as start, stop, exec, logs, and inspect.
- Troubleshoot common container issues including networking, volumes, and port mapping.
- Understand how to use environment variables, expose ports, and mount volumes in containers.
- Apply these practices in a multi-container setup using Docker Compose.

## Key Questions for Understanding and Troubleshooting

1. **When should we use a single-stage Dockerfile versus a multi-stage Dockerfile?**  
   - What are the pros and cons of each approach?
   - In what scenarios (e.g., quick development vs production deployment) is each one appropriate?

2. **Why should we use distroless or Alpine images in the final stage of a Dockerfile?**  
   - What are the benefits in terms of security and image size?
   - Are there any drawbacks?

3. **What happens if we don’t expose port 8080 in the Dockerfile?**  
   - Will the application still work?
   - How does this impact container accessibility from the host or other containers?

4. **Why do we need Docker volumes?**  
   - What happens to application data when the container restarts or is deleted?
   - How do volumes help in development and production environments?

5. **How do we troubleshoot an application that is running inside a container but is failing to connect to a database container?**  
   - What steps would you take to debug this?
   - How can Docker networks and container logs help here?

6. **Why do companies use multi-stage builds in real-world projects?**  
   - What advantages do they bring to startups focused on fast delivery?
   - How do mid-sized companies use them in CI/CD pipelines?

7. **How can we monitor the health and behavior of a container in real-time?**  
   - Which commands help us view logs and inspect the container state?
   - How do health checks improve observability in Compose setups?

 This makes the optimization benefits very clear to the learners.


