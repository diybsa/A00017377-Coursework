[Home](index.md) | [Week 1](week1.md) | [Week 2](week2.md) | [Week 3](week3.md) | [Week 4](week4.md) | [Week 5](week5.md) | [Week 6](week6.md) | [Week 7](week7.md)

# Week 3 – Application Selection for Performance Testing

## 1. Choosing Applications to Test

For performance testing, I need different types of workloads.  
I chose these applications:

| Application | Type of Test | Why I chose it |
|------------|--------------|----------------|
| stress-ng  | CPU + Memory | Good for stressing CPU and RAM |
| fio        | Disk I/O     | Tests disk reading and writing |
| iperf3     | Network      | Tests network speed |
| nginx      | Server load  | Real web server to test requests |

These tools are simple to install, work from terminal, and are often used for testing Linux performance.

---

## 2. How I will install them (via SSH)

I will install each tool using these commands on the server:
sudo apt update
sudo apt install stress-ng
sudo apt install fio
sudo apt install iperf3
sudo apt install nginx

All installations are done through SSH from my Windows workstation.

---

## 3. Expected Performance Results (before testing)

| Application | CPU | RAM | Disk | Network |
|-------------|-----|-----|------|---------|
| stress-ng   | High | Medium | Low | Low |
| fio         | Low  | Low | High | Low |
| iperf3      | Low  | Low | Low | High |
| nginx       | Medium | Medium | Medium | Medium |

This table helps me predict what the system will be doing so I know what metrics to watch.

---

## 4. How I will monitor each one

- **stress-ng** → watch CPU and memory using `top`
- **fio** → check disk usage using `iostat`
- **iperf3** → check network throughput
- **nginx** → monitor requests and CPU usage

All monitoring will be done remotely using SSH.

---

## Reflection

This week I selected the tools I will use for performance testing. I now understand which tool stresses which part of the system. This will help me collect useful results in Week 6 when I run the actual tests.
