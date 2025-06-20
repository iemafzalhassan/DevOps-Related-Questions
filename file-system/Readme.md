##### Blog to read: [Here](https://iemafzalhassan.notion.site/Linux-Operating-System-The-Foundation-of-DevOps-Engineering-12583d10a86f8055a898f01ff1db47bb?source=copy_link)

## **🧠 Assignment: Linux File System – DevOps Interview Practice Questions**

### 🔹 **Basic Understanding**

1. What is a Linux file system? Why is it important in DevOps?
2. Explain the difference between `/`, `/home`, `/etc`, `/var`, and `/usr` directories.
3. What is the role of `inodes` in the Linux file system?
4. What is the difference between a file and a directory in Linux?
5. What happens when you mount a file system? What is a mount point?

---

### 🔹 **Intermediate Level**

6. What is journaling in file systems like ext4 or XFS? Why is it useful?
7. How do you mount and unmount a file system manually? Explain with commands.
8. What’s the purpose of the `/etc/fstab` file in Linux?
9. What are some common mount options and what do they do? (e.g., `noatime`, `ro`, `nosuid`)
10. What’s the difference between `mount` and `bind mount`?

---

### 🔹 **File Systems in Depth**

11. Compare **ext4**, **XFS**, **Btrfs**, and **ZFS**. When would you choose one over the other?
12. Which file system would you use for:

    * A media server handling large video files?
    * A database server requiring snapshots?
    * A basic web server with limited resources?
13. What is the maximum file size and volume size supported by ext4?
14. What’s the difference between a **snapshot** and a **backup**?
15. Which file systems support compression and deduplication?

---

### 🔹 **DevOps & Real-World Relevance**

16. How does the file system impact Docker and Kubernetes volumes?
17. Why is understanding file systems important when configuring persistent storage in containers?
18. What file system would you prefer for storing logs in a CI/CD environment?
19. What are the pros and cons of using exFAT or NTFS in a Linux + Windows dual setup?
20. How do file system permissions affect CI/CD pipeline security?

---

### ✍️ Optional (Bonus for Hands-on)

* Create and format a new partition with the ext4 file system.
* Mount it at `/mnt/demo` and make it auto-mount on boot using `/etc/fstab`.

---


>
> ### Create a post about it and post it on LinkedIn, mentioning TrainWithShubhamCommunity session you've attended and learned about file system.


#### Resources:

- [Linux foundation](https://www.linuxfoundation.org/blog/blog/classic-sysadmin-the-linux-filesystem-explained)
- [Phoenixnap](https://phoenixnap.com/kb/linux-file-system)
