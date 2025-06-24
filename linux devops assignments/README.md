#### **Assignment 1: Log Rotation & Analysis**

**Objective:** Set up log rotation for an application generating logs in `/var/log/myapp/`.

- Configure `logrotate` to:
    
    - Rotate logs daily.
        
    - Retain logs for 14 days.
        
    - Compress old logs.
        
- Write a script to email an alert if a log file exceeds 100MB.
    
- Bonus: Use `awk` or `grep` to extract “ERROR” lines from the last rotated file.

#### **Assignment 2: Process Monitoring with Alerts**

**Objective:** Ensure critical processes stay alive.

- Write a script that checks if `nginx`, `docker`, and `mysqld` are running.
    
- If any is not running:
    
    - Restart the service.
        
    - Send a Slack or email alert.
        
- Automate it using `cron`.

#### **Assignment 3: Permission & Ownership Challenge**

**Scenario:** A teammate gives full access (`chmod 777`) to a web root directory.  
**Task:**

- Find all files/folders with `777` in `/var/www/html`.
    
- Change them to appropriate permissions (`755` for dirs, `644` for files).
    
- Ensure only `www-data` owns the directory recursively.


#### **Assignment 4: Disk Cleanup & Automation**

**Objective:** Automate disk usage management.

- Identify top 10 largest files in `/home` or `/var`.
    
- Delete `.log` or `.tmp` files older than 10 days in `/tmp` or `/var/tmp`.
    
- Set this script to run weekly via cron.


#### **Assignment 5: Firewall & Port Management**

**Objective:** Secure a Linux host.

- Allow ports `22`, `80`, `443`, and deny all others using `ufw` or `iptables`.
    
- Verify SSH is only allowed from a specific IP range.
    
- Write rules to persist across reboot.



# Some Real-Life Linux Q&A for DevOps Engineers

#### **Q1:** You are running out of inodes on `/var`. How do you investigate and fix it?

**Answer:**

- Use `df -i` to check inode usage.
    
- Find culprit: `find /var -xdev -type f | cut -d/ -f3 | sort | uniq -c | sort -nr | head`.
    
- Delete unnecessary small temp files.
    
- Preventive: Monitor inode usage via `cron` + alerting.



#### **Q2:** Your Docker builds are failing with “no space left on device.” How do you debug and fix it?

**Answer:**

- Check disk usage: `df -h` and `du -sh /*`.
    
- Clean:
    
    - `docker system prune -a`.
        
    - Remove old images: `docker rmi $(docker images -f dangling=true -q)`.
        
- Check `/var/lib/docker` for buildup.
    
- Automate weekly cleanup script.


#### **Q3:** How would you analyze a sudden spike in CPU usage on a Linux server?

**Answer:**

- Tools: `top`, `htop`, `pidstat`, `ps aux --sort=-%cpu | head`.
    
- Use `strace -p <pid>` to trace syscalls.
    
- Analyze logs `/var/log/syslog`, `dmesg`, application logs.
    
- If Java, use `jstack`, for Python use `py-spy`.


#### **Q4:** Your `cron` job isn’t running. How do you debug?

**Answer:**

- Check user’s cron: `crontab -l`.
    
- Ensure script is executable.
    
- Redirect stderr: `>> /tmp/myscript.log 2>&1`.
    
- Check `/var/log/cron`, `/var/log/syslog` or `journalctl -u cron`.