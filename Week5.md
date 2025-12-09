[Home](index.md) | [Week 1](week1.md) | [Week 2](week2.md) | [Week 3](week3.md) | [Week 4](week4.md) | [Week 5](week5.md) | [Week 6](week6.md) | [Week 7](week7.md)

# Week 5 – Advanced Security & Monitoring

This week I added more security tools to protect the server and I created two scripts that will help me check security and monitor performance.

---

## 1. AppArmor (Access Control)

Ubuntu Server already includes AppArmor by default.  
I checked the status using:
sudo aa-status

This shows which security profiles are running and if they are enforcing.  
AppArmor helps protect services like SSH and nginx from doing anything outside their allowed rules.

---

## 2. Automatic Security Updates

I installed automatic security updates so the system stays patched:
sudo apt install unattended-upgrades
sudo dpkg-reconfigure unattended-upgrades

This means security updates install automatically without me doing anything.

---

## 3. fail2ban (Blocks Attackers)

Fail2ban blocks IP addresses that try too many wrong passwords.  
I installed it using:
sudo apt install fail2ban

Then I enabled the SSH protection inside its config.  
This gives extra protection against brute-force attacks.

---

## 4. Security Baseline Script

I created a script called `security-baseline.sh` that checks:

- if SSH root login is disabled
- if password login is disabled
- if the firewall is active
- if fail2ban is running
- if automatic security updates are enabled
- if AppArmor is enforcing

I can run it using:
bash security-baseline.sh

This gives a quick security check.

---

## 5. Monitoring Script

I created a script called `monitor-server.sh`.  
This script collects performance information such as:

- CPU load
- memory usage
- disk usage

It does this through SSH from my workstation and saves results into a file.
Later I can use this data to make charts in Week 6.

---

## Reflection (Short)

This week I added multiple security layers to protect the server. I also made scripts to automatically check if my security settings are correct and to monitor performance. These tools will help me in Week 6 and Week 7.
