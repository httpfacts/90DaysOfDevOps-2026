# Day 03 – Linux Commands Cheat Sheet

## Process Management

- `ps aux` – show all running processes
- `top` – live view of CPU and memory usage
- `htop` – improved interactive version of top
- `kill <PID>` – terminate a process by PID
- `kill -9 <PID>` – force kill a process
- `pkill <name>` – kill process by name
- `bg` – resume process in background
- `fg` – bring background process to foreground

---

## File & Directory Management

- `ls` – list files and directories
- `ls -la` – detailed list including hidden files
- `pwd` – show current directory
- `cd` – change directory
- `mkdir <dir>` – create directory
- `rm <file>` – delete file
- `rm -r <dir>` – delete directory recursively
- `cp <src> <dest>` – copy files
- `mv <src> <dest>` – move or rename files
- `touch <file>` – create empty file
- `cat <file>` – view file content
- `less <file>` – view large files safely
- `chmod` – change file permissions
- `chown` – change file ownership

---

## Disk & System Info

- `df -h` – disk space usage
- `du -sh <dir>` – size of directory
- `free -h` – memory usage
- `uptime` – system running time and load
- `uname -a` – system information

---

## Networking & Troubleshooting

- `ping <host>` – check network connectivity
- `ip addr` – view IP addresses and interfaces
- `curl <url>` – test HTTP/API response
- `ss -tuln` – check listening ports
- `netstat -tulnp` – network connections (legacy)

---

## Logs & Services

- `systemctl status <service>` – check service status
- `systemctl restart <service>` – restart a service
- `journalctl -xe` – view system logs
- `journalctl -u <service>` – logs for specific service
