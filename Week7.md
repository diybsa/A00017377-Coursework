[Home](index.md) | [Week 1](week1.md) | [Week 2](week2.md) | [Week 3](week3.md) | [Week 4](week4.md) | [Week 5](week5.md) | [Week 6](week6.md) | [Week 7](week7.md)

# Week 7 – Security Audit & Final Evaluation

This week I checked my whole server to make sure the security configurations were correct. I also ran some security tools to look for weaknesses and confirmed which services are running.

---

## 1. Lynis Security Scan

I installed Lynis:
sudo apt install lynis

Then ran the system audit:
sudo lynis audit system

Lynis gave me a score and some suggestions. 
I can mention:
- issues found
- issues fixed
- improvements after configuration

This shows how secure the system is overall.

---

## 2. nmap Network Scan

From my workstation I scanned the server:
nmap SERVER-IP

Expected open ports:
- 22 (SSH)
- 80 (nginx)

If other ports appeared, I would investigate them.

This confirms the firewall is working properly.

---

## 3. Access Control Check

I checked AppArmor again:
sudo aa-status

I confirmed:
- AppArmor profiles are loaded
- SSH and nginx are enforced
- fail2ban is running

---

## 4. Service Review

I checked which services are running:
systemctl list-unit-files --type=service --state=enabled

If a service was not needed, I disabled it.  
Only essential services are running:
- sshd
- nginx (for testing)
- fail2ban
- unattended-upgrades

---

## 5. Remaining Risks

Even with security tools installed, there are always risks, for example:
- unknown vulnerabilities
- configuration mistakes
- losing SSH keys

To reduce these risks:
- keep the system updated
- keep backups of SSH keys
- check logs and security alerts occasionally

---

## Final Reflection

Over the 7 weeks, I learned how to:
- install and configure a Linux server
- secure SSH access
- apply multiple security layers
- monitor performance
- test different workloads
- evaluate security levels

I gained confidence using command-line tools and remote administration. I now understand how operating systems behave under load, and how to balance security with performance.
