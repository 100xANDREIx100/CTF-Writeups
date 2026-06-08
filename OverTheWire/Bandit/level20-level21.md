# OverTheWire - Bandit - Level 20 -> Level 21

## 🎯 Objective
Setup a port to listen and connect to it

## 🛠️ Tools & Concepts Used
* `nc -l -p` - make a port listen and wait for incoming communication 

## 📝 Step-by-Step Solution

**1. Make a port to listen**
I had to first provide to a listening port the password of the last level and make it wait for a connection

```bash
echo "0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO" | nc -l -p 12345 &
```
IN the same time I moved the process in the background so I would be able to connect to this port using the provided utilitary

**2. Connect to that port**
Then, all left was just to connect to that port 

```bash
./suconnect 12345
```
BY establishing the connection I received the password.

## 💡 Key Takeaway
Learned how to make a port listen using `nc`
