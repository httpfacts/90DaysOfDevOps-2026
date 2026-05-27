# Day 02 – Linux Architecture, Processes & systemd

## What is Linux?
- Linux is an **Operating System**
- Used mostly in **production environments**
- Why?
  - Stable
  - Secure
  - Lightweight
- That’s why most servers run Linux

---

## Where do we use Linux?
- Cloud servers (AWS EC2, Azure VM, etc.)
- On-prem servers
- Containers
- Local setup (Ubuntu, WSL, dual boot)

---

## Why Linux for DevOps?
- Most DevOps tools run on Linux
- Servers = Linux
- Troubleshooting + automation needs Linux basics clear

---

## Linux Architecture 

Linux works in layers:

**Application → Shell → Kernel → Hardware**  
(ASK – easy to remember)

### Application
- User programs (nginx, docker, git, python)
- Cannot talk to hardware directly

### Shell
- Medium between user and OS
- Takes commands and passes them to kernel
- Example: bash

### Kernel
- Core of Linux
- Handles:
  - CPU
  - Memory
  - Processes
  - Devices
- Talks directly to hardware

### Hardware
- CPU, RAM, Disk, Network

---

## Linux File System Basics
- In Linux, **everything is a file or directory**

Important ones:
- `/bin`  → basic user commands
- `/sbin` → system level commands
- `/etc`  → configuration files
- `/mnt`  → mount points
- `/var`  → logs and variable data
- `/home` → user data

(Rest can be checked using `man`)

---

## Process Management

### What is a process?
- A running program

### How process is created
- User runs command
- Shell sends it to kernel
- Kernel assigns PID and resources

### Process States
- **Running (R)** – currently executing
- **Sleeping (S)** – waiting for I/O
- **Stopped (T)** – paused
- **Zombie (Z)** – finished but not cleaned

---

## systemd
- `systemd` is the **first process** (PID 1)
- Starts during system boot

### What systemd does
- Starts services
- Stops services
- Restarts failed services
- Manages boot order

### Why it matters
- All production services are managed by systemd
- Used daily in troubleshooting

---

## Daily Use Linux Commands
- `ps` – check processes
- `top` / `htop` – live system usage
- `systemctl` – manage services
- `journalctl` – check logs
- `df` / `du` – disk usage

---

## Final Note
- Linux = base of DevOps
- Kernel does the real work
- systemd controls services
- Process understanding is key for debugging