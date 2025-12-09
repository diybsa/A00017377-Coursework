[Home](index.md) | [Week 1](week1.md) | [Week 2](week2.md) | [Week 3](week3.md) | [Week 4](week4.md) | [Week 5](week5.md) | [Week 6](week6.md) | [Week 7](week7.md)

# Week 1 – System Planning & Setup

## 1. System Architecture (Simple Explanation)

I am using two systems:

- **Server:** Ubuntu Server 22.04 LTS (headless, no GUI), running in VirtualBox.
- **Workstation:** My Windows computer. I will use PowerShell to connect via SSH.

The idea is that all server management must be done remotely from the Windows machine.

## 2. Why I Chose Ubuntu Server 22.04

- It is stable and has Long-Term Support.
- It is easy to install and well documented.
- Works well for security tools like UFW, AppArmor, fail2ban.
- Commonly used in real servers.

## 3. Workstation Choice (Option B)

I chose **Option B** – use my Windows PC as the workstation.

Reason:
- No need to run two VMs.
- Windows already has an SSH client.
- Simple and efficient.

## 4. Network Setup (Simple)

I will use VirtualBox **Bridged Adapter** so my VM gets an IP like:
192.168.x.x

Then I can connect using:
ssh username@VM-IP

I will update the exact IP after installation.

## 5. Basic System Information Commands

Once Ubuntu Server is installed, I ran these commands (I will insert my real outputs later):
uname -a
free -h
df -h
ip addr
lsb_release -a

These commands show:
- Kernel version  
- RAM  
- Disk space  
- IP address  
- Ubuntu version  

## 6. Reflection 

This week I planned the setup and understood how the server and workstation will communicate.  
I also confirmed why Ubuntu Server is the best option and learned how to check system details using basic Linux commands.

