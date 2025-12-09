[Home](index.md) | [Week 1](week1.md) | [Week 2](week2.md) | [Week 3](week3.md) | [Week 4](week4.md) | [Week 5](week5.md) | [Week 6](week6.md) | [Week 7](week7.md)

# Week 4 – SSH Setup and Basic Security

This week I started configuring the server and applying basic security controls, all done remotely through SSH from my Windows workstation.

---

## 1. SSH Key Authentication

### Steps I followed:
- I created an SSH key pair on Windows using PowerShell:
ssh-keygen
- I copied the public key to the server and placed it in:
~/.ssh/authorized_keys
- After this, I could log in without a password.

This makes SSH more secure.

---

## 2. Disable Password Login

I edited the SSH configuration file:
sudo nano /etc/ssh/sshd_config

And changed these lines:
PermitRootLogin no
PasswordAuthentication no

Then restarted SSH:
sudo systemctl restart ssh

Now only key-based login works, and root login is blocked.

---

## 3. Create a Non-Root Admin User

I created another user and gave them admin rights:
sudo adduser adminuser
sudo usermod -aG sudo adminuser

From now on, I will use this account instead of root.

---

## 4. Enable Firewall (UFW)

I turned on the firewall and allowed SSH only from my workstation IP (example IP shown):

sudo apt install ufw
sudo ufw allow from 192.168.1.50 to any port 22
sudo ufw enable

This blocks all other incoming connections.
<img width="529" height="387" alt="image" src="https://github.com/user-attachments/assets/19cdc2ae-7d38-4d2e-8bbb-c3b56d1dfa44" />

---

## 5. Evidence 

I tested SSH login from Windows using:
ssh adminuser@SERVER-IP

I confirmed:
- remote login works
- password login is disabled
- firewall is active
- only my IP can connect

These are the screenshots I will include in GitHub when I finish the setup.

---

## Reflection

This week I learned how to secure SSH using keys, disable passwords, create a safer admin account, and control access using the firewall. I also learned how easy it is to accidentally lock yourself out, so testing step-by-step is important.
