# OverTheWire - Bandit - Level 19 -> Level 20

## 🎯 Objective
Use the `setuid` binary file

## 🛠️ Tools & Concepts Used
* `setuid` - run an executable file with the permissions of the configured profile

## 📝 Step-by-Step Solution

**1. Use the executable**
To read the password I had give the proper command using the executable

```bash
./bandit20-do cat /../../etc/bandit_pass/bandit20
```
The output was the password for the next level

## 💡 Key Takeaway
Learned how to use `setuid`
