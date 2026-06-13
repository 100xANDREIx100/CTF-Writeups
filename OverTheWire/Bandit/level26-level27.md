# OverTheWire - Bandit - Level 26 -> Level 27

## 🎯 Objective
Use escalated identity to get the next password

## 🛠️ Tools & Concepts Used
* `bash` - interactive command interpreter and command language 

## 📝 Step-by-Step Solution

**1. Run the script**
After running the script blindly (`./bandit27-do`) and knowing where the flags are stored (`/etc/bandit_pas/bandit27`), I just had to run it with the proper arguments

```bash
#!/usr/bin/env bash
./nadit27-do cat /../../etc/bandit_pass/bandit27
```
It directly outputted the password for the next level

## 💡 Key Takeaway
Refreshed priviladge escalation
