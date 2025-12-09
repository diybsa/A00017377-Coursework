[Home](index.md) | [Week 1](week1.md) | [Week 2](week2.md) | [Week 3](week3.md) | [Week 4](week4.md) | [Week 5](week5.md) | [Week 6](week6.md) | [Week 7](week7.md)

# Week 2 – Security Planning & Testing Plan

## 1. Performance Testing Plan

I will test how the Linux server performs under different workloads by running tests using the command line and monitoring everything through SSH.

I will measure:
- CPU usage  
- Memory usage  
- Disk performance  
- Network performance  

Tools I plan to use:
- `top` or `htop` (CPU and RAM)
- `free` (memory)
- `df -h` (disk space)
- `iostat` (disk performance)
- `ping` (latency)
- `iperf3` (network throughput)

I will run tests for:
- Baseline (idle server)
- Load (stress tests)
- Optimisation (after changing settings)

All monitoring will be done from my Windows workstation using SSH.

---

## 2. Security Checklist (What I plan to secure)

### SSH security:
- disable root login
- disable password login
- allow key authentication only
- only allow SSH from my workstation IP

### Firewall:
- enable UFW
- deny all incoming connections by default
- allow only SSH (from my workstation IP)
- allow required ports later (e.g. for nginx)

### Access Control:
- use AppArmor (already included in Ubuntu)
- check profile status for services

### Automatic Updates:
- enable unattended upgrades

### Users:
- create a non-root admin user
- use sudo
- no direct root login

### Network:
- disable unnecessary services
- check open ports
- install fail2ban

---

## 3. Threat Model 

### Threat 1: Brute-force SSH attacks
Attackers might try lots of passwords.
**Solution:** Disable passwords, only use SSH keys, block failed attempts.

### Threat 2: Unpatched software
Out-of-date services could be hacked.
**Solution:** Automatic security updates and regular upgrades.

### Threat 3: Misconfiguration
Wrong permissions or services running.
**Solution:** Firewall rules, AppArmor profiles, fail2ban, checking open ports.

---

## Reflection 

This week I planned my security setup before changing anything. I wrote a checklist and identified possible security threats. This helps make sure my system becomes secure step by step and reduces the chance of mistakes later.
<img width="739" height="492" alt="image" src="https://github.com/user-attachments/assets/75f67b52-e0cb-484a-8ebf-5699df866aec" />
