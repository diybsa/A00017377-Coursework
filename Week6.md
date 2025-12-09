[Home](index.md) | [Week 1](week1.md) | [Week 2](week2.md) | [Week 3](week3.md) | [Week 4](week4.md) | [Week 5](week5.md) | [Week 6](week6.md) | [Week 7](week7.md)

# Week 6 – Performance Testing

This week I used the tools I selected earlier to test how my Linux server performs under different types of workloads (CPU, RAM, disk, network, and web server).

All tests were done through SSH from my Windows workstation.

---

## 1. Testing Method 

For each application, I did:

- Baseline test (when server is idle)
- Load test (using stress tools)
- Collected performance numbers
- Tried small optimisations
- Compared results

I monitored:
- CPU usage
- Memory usage
- Disk load
- Network traffic

---

## 2. Example Commands I Used

CPU test:
stress-ng --cpu 4 --timeout 60s

Memory test:
stress-ng --vm 1 --vm-bytes 80%
Disk test:
fio --name=test --rw=readwrite --bs=4k --size=500M
Network test:
iperf3 -s (on server)
iperf3 -c SERVER-IP (on workstation)
Web server load:
ab -n 1000 -c 50 http://SERVER-IP/

---

## 3. Example Results Table (I will replace with my real results)

| Test | What I tested | Example result |
|------|--------------|----------------|
| CPU  | stress-ng    | High CPU load |
| RAM  | stress-ng    | High memory usage |
| Disk | fio          | High disk I/O |
| Net  | iperf3       | High network throughput |
| Web  | nginx + ab   | High traffic |

This table will be updated with real data after I finish testing.

---

## 4. Performance Charts

My monitoring script saved performance values to a file.  
Later I will turn these into charts such as:

- CPU usage over time
- RAM usage over time
- Network throughput

(Charts will be added after I finish collecting real numbers.)

---

## 5. Optimisation (2 examples)

### Example 1 – Lower swappiness
sudo sysctl vm.swappiness=10
Helps the system avoid swapping too early.

### Example 2 – nginx worker changes
I increased nginx worker connections to handle more load.

---

## Reflection 

This week I learned how different workloads affect different parts of the operating system. Small changes can make performance better. I also saw how important monitoring data is for understanding what is happening inside the server.
