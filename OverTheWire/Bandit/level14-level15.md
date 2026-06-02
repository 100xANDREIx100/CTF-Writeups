# OverTheWire - Bandit - Level 14 -> Level 15

## 🎯 Objective
Use a private ssh key to log into the next level

## 🛠️ Tools & Concepts Used
* `nc` - create a network connection

## 📝 Step-by-Step Solution

**1. Connect to localhost**
Once logged in, I connected to localhost on the required port

```bash
nc localhost 30000
```

**2. Sending the password**
There, I just had to send the previous password without anything extra

## 💡 Key Takeaway
Learned how to use `nc` in order to connect toa specieid port of an interface
