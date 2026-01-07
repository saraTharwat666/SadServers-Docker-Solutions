# 🛠️ Infrastructure & DevOps Troubleshooting Lab

![Infrastructure as Code](https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExM3Z6Z3R6Z3R6Z3R6Z3R6Z3R6Z3R6Z3R6Z3R6Z3R6Z3R6Z3JmJmVwPXYxX2ludGVybmFsX2dpZl9ieV9pZ25vcmUmY3Q9Zw/u04b5LggXzO9uTSvSS/giphy.gif)

## 📌 Executive Summary
This repository serves as a professional technical log for resolving complex infrastructure failures and system misconfigurations. Each scenario is sourced from **SadServers** and focuses on real-world DevOps bottlenecks.

The primary objective is to demonstrate a systematic approach to **Root Cause Analysis (RCA)** and infrastructure recovery.

---

## 📂 Troubleshooting Registry

| Scenario | Difficulty | Tech Stack | Documentation |
| :--- | :--- | :--- | :--- |
| **Helsingør** | Medium | PostgreSQL, Docker-Compose, Replication | [Analysis & Fix](./Helsingor-Postgres-Replication/) |
| **Salta** | Medium | Dockerization, Node.js, Port Mapping | [Analysis & Fix](./Salta-Nodejs-App/) |
| **Saint John** | Easy | Linux Kernel, Process Mgmt, Log Rotation | [Analysis & Fix](./Saint-John-Log-Killer/) |

---

## 🛠️ Tech Stack & Methodologies
![Docker Workflow](https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExNmtpZ3R6Z3R6Z3R6Z3R6Z3R6Z3R6Z3R6Z3R6Z3R6Z3R6Z3JmJmVwPXYxX2ludGVybmFsX2dpZl9ieV9pZ25vcmUmY3Q9Zw/3o7TKVUn7iM8FMEU24/giphy.gif)

### Core Competencies Demonstrated:
* **Container Orchestration:** Debugging Docker daemon, networking, and volume persistence.
* **Database Reliability:** Configuring Physical Replication slots and WAL parameters in PostgreSQL.
* **System Internal:** Investigating file descriptors, PID tracking, and disk I/O bottlenecks.
* **Log Analysis:** Utilizing `journalctl`, `docker logs`, and `lsof` for rapid incident response.

---
**Maintained by a DevOps Engineer focused on System Stability and Automation.**
