# OverTheWire - Bandit - Level 10 -> Level 11

## 🎯 Objective
Decode the base64 file

## 🛠️ Tools & Concepts Used
* `base64 -d` - decodes a file from base64 to ASCII
## 📝 Step-by-Step Solution

**1. Decode the file**
Once logged in, I decoded the file from base64 using the specific command. At first I tought about copying its text and decoding it using a web app like `cyberchef` but I found an easier way.

```bash
base64 -d data.txt
```
There, I just got the passoword.

## 💡 Key Takeaway
Refreshed basic commands.