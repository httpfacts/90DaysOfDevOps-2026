# Linux Troubleshooting Runbook – Day 05

## Target Service / Process
ssh (sshd)

---

## Environment Basics

```bash
uname -a
lsb_release -a
```

![image](image1.png)

**Observation:**  
Kernel version and Ubuntu OS details identified successfully.

---

## Filesystem Sanity

```bash
mkdir /tmp/runbook-demo
cp /etc/hosts /tmp/runbook-demo/hosts-copy
ls -l /tmp/runbook-demo
```

![image](image2.png)

**Observation:**  
Filesystem is writable. Directory creation and file copy operations work as expected.

---

## Snapshot: CPU & Memory

```bash
ps -eo pid,pcpu,pmem,comm | grep ssh
free -h
```

![image](image3.png)

**Observation:**  
SSH process shows minimal CPU and memory usage. No memory pressure observed.

---

## Snapshot: Disk & I/O

```bash
df -h
du -sh /var/log 2>/dev/null
```

![image](image4.png)

**Observation:**  
Disk usage is within safe limits. Log directory size is normal.

---

## Snapshot: Network

```bash
ss -tulpn | grep :22
curl -I localhost
```

![image](image5.png)

**Observation:**  
SSH service is listening on port 22. Local network stack is responsive.

---

## Logs Reviewed

```bash
journalctl -u ssh -n 50 --no-pager
```

![image](image6.png)

**Observation:**  
No recent SSH service errors or crashes found.

---

## Authentication Logs

```bash
tail -n 50 /var/log/auth.log
```

![image](image7.png)

**Observation:**  
Authentication logs show normal login activity with no suspicious behavior.

---

## Target Service Confirmation

```bash
systemctl status ssh
```

![image](image8.png)

**Observation:**  
SSH service is active and running normally.

---

## Quick Findings
- SSH service is healthy and stable
- No abnormal CPU, memory, disk, or network usage
- Logs indicate normal system behavior

---

## If This Worsens (Next Steps)
1. Restart SSH service and monitor logs  
2. Increase SSH log verbosity for debugging  
3. Use monitoring or tracing tools (top, vmstat, strace)

---

## End of Runbook