<p align="center">
  <img src="https://i.imgur.com/YOUR_BANNER.jpg" alt="LinuxOps DevOps Project" width="90%">
</p>

## 📐 Filesystem Architecture Diagram

<p align="center">
  <img src="https://i.imgur.com/YOUR_DIAGRAM.jpg" alt="Linux Filesystem Diagram" width="85%">
</p>


# **LinuxOps – DevOps Project**

### *Server Automation & Security | Hands-on Linux Lab*

This repository contains a **practical LinuxOps / DevOps lab** focused on **real Linux fundamentals**:

* User & group management
* Permissions & ownership
* Directory and file operations
* Text processing (`sed`, `vi`)
* System inspection commands
* Cleanup & hygiene

> 🎯 **Goal**: Learn Linux by *doing*, not copy‑pasting.

---

## 🚀 Quick Start (Run This First)

### **Run Ubuntu Linux Container (Persistent & Long‑Term)**

```bash
docker run -dit \
--name ubuntu-container \
--hostname ubuntu-dev \
--restart unless-stopped \
--cpus="2" \
--memory="4g" \
--mount type=bind,source=/tmp/ubuntu-data,target=/data \
-v /var/run/docker.sock:/var/run/docker.sock \
-p 2222:22 \
-p 8080:80 \
--env TZ=Asia/Kolkata \
--env LANG=en_US.UTF-8 \
ubuntu:latest /bin/bash
```

Enter the container:

```bash
docker exec -it ubuntu-container bash
```

---

## 🧠 Docker Parameters Explained

| Parameter                                                | Description                               |
| -------------------------------------------------------- | ----------------------------------------- |
| `-dit`                                                   | Detached + interactive terminal           |
| `--name ubuntu-container`                                | Container name                            |
| `--hostname ubuntu-dev`                                  | Hostname inside container                 |
| `--restart unless-stopped`                               | Auto‑restart policy                       |
| `--cpus="2"`                                             | CPU limit                                 |
| `--memory="4g"`                                          | Memory limit                              |
| `--mount type=bind,source=/tmp/ubuntu-data,target=/data` | Persistent storage                        |
| `-v /var/run/docker.sock:/var/run/docker.sock`           | Docker access inside container (optional) |
| `-p 2222:22`                                             | SSH port mapping                          |
| `-p 8080:80`                                             | Web service port                          |
| `--env TZ=Asia/Kolkata`                                  | Timezone                                  |
| `--env LANG=en_US.UTF-8`                                 | Locale                                    |
| `ubuntu:latest /bin/bash`                                | Ubuntu image + Bash                       |

---

## 🧪 Deployment Steps

### **Step 1 – Initial Setup (root)**

1. Create users: `Dev1`, `Dev2`, `Dev3`
2. Create groups: `devops`, `aws`, `management`, `sales`
3. Change primary group of `Dev2`, `Dev3` → `devops`
4. Add `aws` as secondary group to `Dev1`
5. Create directory & file structure (as per diagram)
6. Change group of `/dir1`, `/dir8/dir9`, `/f2` → `devops`
7. Change ownership of `/dir1`, `/dir8/dir9`, `/f2` → `Dev1`

---

### **Step 2 – Additional Users & Groups (root)**

1. Create users: `Dev4`, `Dev5`
2. Create groups: `app`, `database`

---

### **Step 3 – File Operations**

1. **root**: Create file `/f3`
2. **root**: Rename `/f2` → `/f4`
3. **Dev4**: Move `/dir1/f1` → `/dir2/dir1/dir2`

---

### **Step 4 – Advanced Filesystem Tasks**

1. **root**: Create `/home/Dev2/dir1`
2. **root**: From `/dir2/dir1/dir2/dir10`, create `/opt/dir12/dir10/f1` using *relative path*
3. **root**: Delete `/dir4` recursively
4. **root**: Delete all child items under `/opt/dir12`
5. **Dev1**: Move `/opt/dir12/dir10/f1` → `/home/Dev1`
6. **root**: Write text to `/f3`

---

### **Step 5 – Text Processing & Cleanup**

1. **root**: Create `/dir1/f2`
2. **root**: Delete `/dir6`
3. **root**: Delete `/dir8`
4. **root**: Replace `DevOps` → `devops` in `/f3`
5. **root**: Using `vi`, copy line 1 and paste it 10 times
6. **root**: Replace `Engineer` → `engineer`
7. **root**: Delete `/f3`

---

### **Step 6 – System Inspection (root)**

1. Search file `f3` (absolute paths)
2. Count files in `/`
3. Print last line of `/etc/passwd`

---

### **Step 7 – Filesystem Verification**

1. Verify filesystem usage using `df -h`
2. Create `/data/f1`

> ⚠️ **Docker Note**: `mount` / `umount` are restricted in standard Docker containers.

---

### **Step 8 – Final Cleanup (root)**

1. Delete `/dir1`, `/dir2`, `/dir3`, `/dir5`, `/dir7`
2. Delete `/f1`, `/f4`
3. Delete `/opt/dir12`

---

### **Step 9 – User & Group Cleanup (root)**

1. Delete users: `Dev1`, `Dev2`, `Dev3`, `Dev4`, `Dev5`
2. Delete groups: `app`, `aws`, `database`, `devops`, `management`, `sales`
3. Remove remaining home directories (if any)

---

## 🐳 Docker vs VM Compatibility

| Feature             | Docker | VM / EC2 |
| ------------------- | ------ | -------- |
| Users & groups      | ✅      | ✅        |
| Files & permissions | ✅      | ✅        |
| Text processing     | ✅      | ✅        |
| mount / umount      | ❌      | ✅        |

---

## 🔗 Connect with Me

* **GitHub**: [https://github.com/piyush-pooh](https://github.com/piyush-pooh)
* **LinkedIn**: [https://www.linkedin.com/in/piyush-sharma-5250a0291/](https://www.linkedin.com/in/piyush-sharma-5250a0291/)
* **Twitter (X)**: [https://x.com/Piyush_poooh](https://x.com/Piyush_poooh)

---

## ⭐ Support the Project

If this lab helped you **understand Linux the right way**, please ⭐ **star the repository** and share it 🚀

> *LinuxOps mindset: Don’t fight Linux. Understand it.*


