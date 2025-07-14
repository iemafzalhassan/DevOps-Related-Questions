### 1. What is WSL and how does it help run Linux environments inside Windows?

WSL (Windows Subsystem for Linux) is a compatibility layer developed by Microsoft that allows you to run a Linux environment directly on Windows, without needing a virtual machine or dual-boot setup.

### Some keypoints:- 
* WSL enables developers to use Linux command-line tools, utilities, and applications natively on a Windows machine.

* It integrates tightly with Windows, so you can access Linux files from Windows and vice versa.

* We can run popular tools like bash, git, curl, ssh, apt, and more.


### 2. What is Docker and why is it preferred over VMs for app deployment today?

Docker is an Open source platform that allows us to package our applications with all the dependencies and create, run our container in isolated environment. It solves the problem that "It is working in your machine not in mine machine".

VM:- virtual machine is more heavy than containers because it does not share kernel and other reasources, it uses seprate OS per VM.
* it takes minutes to boot 

Container:- containers is more lightweighted than VM because it shares host's kernel and it directly uses OS of Host
* it takes only seconds to boot
*  A Docker container includes everything an app needs:
✅ Code
✅ Dependencies
✅ System libraries
✅ Configuration files

This ensures the app runs the same regardless of where it is deployed — on a developer’s laptop, a test server, or a production cloud server.

### 3. What are the limitations of using WSL for production workloads?

* Not a real Linux host	 = WSL is a compatibility layer on top of Windows, not a full Linux distribution.

* No systemd support (WSL 1) =	Many Linux services depend on systemd. WSL 1 doesn't support it, and WSL 2 only partially supports it with extra config.

* No kernel-level control =	You cannot modify or control the Linux kernel (required for advanced networking, kernel modules, etc.).

* Limited Networking Features =	Network behavior in WSL is different; it's not suitable for apps that require custom networking or advanced firewall rules.

* Less Stable for Long Running Services	=  WSL is tied to the Windows session. Services may stop when the Windows system sleeps, reboots, or logs out.

* Not Meant for Multi-User Access  = Production Linux servers often support multiple users and SSH access. WSL is single-user and not designed for remote access.

* Security Concerns  = Running production services inside a Windows host increases the attack surface and is not best practice.


###  Scenario 1: Docker Container Not Accessible

**Scenario:**

You’ve deployed an NGINX container using the command:

```bash
docker run -d -p 8080:80 nginx
```

But when accessing http://localhost:8080, the browser shows "This site can’t be reached".

Question:
What steps would you take to troubleshoot this issue? Mention how networking works in Docker + WSL.

* Firstly I check conyainer is running or not using 
```
docker ps
```
* then I will ckeck logs of container 
```
docker logs <container-Id>
```

* then I will check conatiner using 
```
docker exec -it <container_id> bash
```
* Then check if the server responds internally:
```
apt update && apt install curl -y
curl http://localhost
```

### If i'm using EC2 then I will check SG that I exposed port no or not 


###  Scenario 2: Docker Installation Issues

**Scenario:**

A teammate tries to install Docker Desktop but gets an error that Hyper-V is disabled, and Docker won’t start.

Question:

What would you check first? How can WSL2 resolve this issue, and what settings should be enabled during installation?

* first i will check WSL is installed or not using
```
wsl --install
```
* if wsl is not installed then install it using 
```
wsl --install
```
* Enable Required Windows Features
Go to "Turn Windows Features On or Off" and check these:

Feature	Status
✅ Virtual Machine Platform	✔ Enable
✅ Windows Subsystem for Linux	✔ Enable
⛔ Hyper-V (Optional)	❌ Can be left unchecked if using WSL 2 backend

* Enable WSL 2 in Docker Desktop
After installation:

Open Docker Desktop

Go to Settings → General

✅ Enable: "Use the WSL 2 based engine"

Go to Settings → Resources → WSL Integration

✅ Enable Docker for your Linux distro (e.g., Ubuntu)

*  Restart and Test
```
docker --version
docker run hello-world
```
if my container runs then docker is working 

