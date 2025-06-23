# 👩‍💻 Linux User Management – Shell Scripting Practice Tasks

This repository contains **hands-on shell scripting exercises** focused on real-world **Linux user management**. These tasks are ideal for students, DevOps beginners, or those preparing for technical interviews.

---

## 📚 Section 1: Beginner Shell Scripting Tasks

### ✅ Q1. Check and Create User If Not Exists

Check if a user named `devuser` exists on the system.

**🛠️ Task:**
- If the user exists, display their home directory and UID  
- If not, create the user with a home directory and bash shell

📌 _Use `id`,  or `grep` to check existence._

---

### 📁 Q2. Bulk Create and Delete Users

You have a file `users.txt` containing usernames:

**🛠️ Task:**
- Write a script to create all users with home directories  
- Later, delete all users and their home directories

📌 _Ensure the script handles errors if a user already exists._

---

### 🔒 Q3. Switch User, Lock, and Unlock

You are onboarding a trainee named `intern1`.

**🛠️ Task:**
- Create the user `intern1` and set a password  
- Switch to `intern1` using `su - intern1` to confirm login works  
- Lock the user account  
- Try switching again and observe the error  
- Unlock the account and confirm login works again

📌 _Use `passwd -S intern1` to check lock status._

---

### 📆 Q4. Create User with Expiry Date

Create a temporary user `demoexp` for a 2-week training session.

**🛠️ Task:**
- Create `demoexp` with home directory and bash shell  
- Set the account to expire after 14 days  
- Confirm the expiry date is applied

📌 _Use `sudo chage -E` and `chage -l demoexp` to verify._

---

### 🛡️ Q5. Create Admin User with Group Setup

Create a user `devopslead` with elevated permissions.

**🛠️ Task:**
- Create user with `/bin/bash` shell  
- Add to `sudo` and `docker` groups  
- Verify with `id` or `groups`

---

### 🧮 Q6. Create User with Custom UID, GID, and Shell

**🛠️ Task:**
- Create `teamalpha` with UID `2501`, GID `2601`  
- Use bash as the default shell  
- Ensure the GID exists or create it

📌 _Use `groupadd -g` and `useradd -u`._

---

### 🗂️ Q7. Set Default Home Directory Location

Place new user homes under `/data/users` instead of `/home`.

**🛠️ Task:**
- Create `custompath` with home `/data/users/custompath`  
- Ensure it’s created and owned correctly

📌 _Use `useradd -d` and `mkdir -p`._

---

### 🧼 Q8. Delete User and Clean Up

Cleanly remove user `oldintern`.

**🛠️ Task:**
- Delete `oldintern` and their home  
- Ensure no background processes are left

📌 _Use `userdel -r` and check `ps -u oldintern`._

---


### 📝 Q9. Rename User and Move Home Directory (Advanced)

You created a user `test123`, but it should be `devqa`.

**🛠️ Task:**
- Rename `test123` to `devqa`  
- Move all files from `/home/test123` to `/home/devqa`  
- Ensure user can still log in

📌 _Use `usermod -l`, `-d`, and `-m` options._
  
 ---

### 🛠️ Q10. Fix User Configuration Mistakes (Advanced)

You created a user `tempuser` with incorrect settings.

**🛠️ Task:**
- Rename to `qaengineer`  
- Change home to `/home/qaengineer` and move files  
- Set shell to `/bin/zsh`  
- Change UID to `1501`  
- Set primary group to `qa` (create if needed)  
- Add to `docker` and `sudo` groups

📌 _Use `usermod`, `groupadd`, and `gpasswd`._

---
