#   Assignment: Linux File System – DevOps Interview Practice Questions 



# 🔹 Basic Understanding ✅ 

## 1. What is a Linux file system? Why is it important in DevOps?
## Answer.. 
Linux file system is the way Linux stores, organizes, and manages files and data on storage devices like hard drives or SSDs.
Yes it's important in DevOps because: DevOps deals with deploying and managing applications on servers. Knowing where and how files are stored helps with automation, monitoring, backups, and troubleshooting. It's key to managing logs files, configurations files, and many more.

## 2. Explain the difference between /, /home, /etc, /var, and /usr directories.?
## Answer..
/  Root: directory. It’s the top of everything in Linux. All files and folders start from here.
/home: Contains personal folders for each user.
/etc: Stores configuration files for the system and installed software.
/var: Stores variable data, like logs, emails, and files.
/usr: Holds user programs and files, like installed software and libraries.

## 3. What is the role of inodes in the Linux file system?
## Answer.. 
An inode is like a files identity card. It stores information about a file, like its size, permissions, and location on disk but not the file name itself.

## 4. What is the difference between a file and a directory in Linux?
## Answer..
A file is a container that holds data like text, images, or code.
A directory is a folder that holds files or other directories inside.

## 5. What happens when you mount a file system? What is a mount point?
## Answer..
Mounting means making a file system like a USB drive or another disk available to the Linux system or other operating system.
A mount point is the folder where you access files and folders.



# 🔹 Intermediate Level ✅ 

## 6. What is journaling in file systems like ext4 or XFS? Why is it useful?
## Answer..
Journaling is a safety feature in file systems like ext4 or XFS. Before making real changes to the disk, it writes those changes in a special journal a kind of log file.
Yes its useful..
if your system crashes or loses, the file system can use the journal to recover quickly and keeps your data safer.

## 7. How do you mount and unmount a file system manually? Explain with commands.
## Answer..
dev/sdX1 is your device like disk partition. /mnt/myfolder is where you want to access the files.
COMMAND..
sudo mount /dev/sdX1 /mnt/myfolder
sudo umount /mnt/myfolder

## 8. What’s the purpose of the /etc/fstab file in Linux?
## Answer..
/etc/fstab is a config file that tells Linux what file systems to mount automatically when the system starts.

## 9. What’s the difference between a normal mount and a bind mount?
## Answer
A normal mount connects a device (like a USB or disk) to a folder.
A bind mount makes a folder appear in another location. That you can access at same time same folder but different location.



# 🔹 File Systems in Depth ✅ 

## 10. Compare ext4, XFS, Btrfs, and ZFS. When would you choose one over the other?
## Answer..
| File System | Best For                                        | Pros                                       | Cons                                               |
| ----------- | ----------------------------------------------- | ------------------------------------------ | -------------------------------------------------- |
| **ext4**    | General use, simple systems                     | Fast, stable, widely used                  | No built-in snapshots or advanced features         |
| **XFS**     | Large files and high-speed writing (like media) | Great performance, handles big files well  | No snapshots, harder to shrink                     |
| **Btrfs**   | Snapshots, backups, testing environments        | Snapshots, compression, copy-on-write      | Still maturing, not as stable under heavy load     |
| **ZFS**     | Enterprise storage, data integrity, backups     | Snapshots, deduplication, error correction | Uses a lot of RAM, not built into Linux by default |

## 11. Which file system would you use for:
## Answer..
A media server handling large video files?
XFS – It’s fast and great with large files.
A database server requiring snapshots?
Btrfs or ZFS – Both support snapshots, but ZFS is more robust.
A basic web server with limited resources?
ext4 – It’s light, reliable, and doesn’t need much RAM or CPU.

## 12. What is the maximum file size and volume size supported by ext4?
## Answer..
Max file size 16 TB.

## 13. What’s the difference between a snapshot and a backup?
## Answer..
Snapshot:
A quick frozen view of a file system at a moment in time. It’s fast and uses little space. Usually stays on the same disk.
Backup:
A copy of your data, stored else where. Safer, because if the main disk fails, your backup is still safe.

## 14. Which file systems support compression and deduplication?
## Answer..
Btrfs and ZFS support compression. ZFS also supports built-in deduplication, while Btrfs can do deduplication with extra tools but it's not built-in or as stable.



# 🔹 DevOps & Real-World Relevance ✅ 

## 15. How does the file system impact Docker and Kubernetes volumes?
## Answer..
The file system affects how fast, safe, and reliable data is stored inside Docker/Kubernetes volumes. Some file systems handle large files, snapshots, or backups better, which is important when containers store logs, databases, or persistent data.

## 16. Why is understanding file systems important when configuring persistent storage in containers?
## Answer..
Because not all file systems are the same. Some support snapshots, fast read/write, or compression. if you pick the wrong one, your app may be slow, lose data, or crash under load.

## 17. What file system would you prefer for storing logs in a CI/CD environment?
## Answer..
XFS or ext4 both are stable and perform well.
XFS is better for large, fast growing log files.
ext4 is simpler and uses less system resources.

## 18. What are the pros and cons of using exFAT or NTFS in a Linux + Windows dual setup?
## Answer..
| File System | Pros                                               | Cons                                           |
| ----------- | -------------------------------------------------- | ---------------------------------------------- |
| **exFAT**   | Works on both Windows & Linux, no file size limits | No file permissions, not journaled (less safe) |
| **NTFS**    | Supports permissions and journaling                | Slower on Linux, needs special drivers         |

## 19. How do file system permissions affect CI/CD pipeline security?
## Answer..
If file permissions are too loose, attackers can read, change, or delete files used in builds or deployments.
Proper permissions make sure only the right scripts and users can access sensitive files, keeping the pipeline safe.

