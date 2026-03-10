# OverTheWire - Bandit - Level 3 -> Level 4

## 🎯 Objective
Find the password in the specified folder

## 🛠️ Tools & Concepts Used
* `ls -a` - list all files including hidden

## 📝 Step-by-Step Solution

**1. List all (hidden) files in current directory**
Once logged in, I needed to see what (hidden) files were available in the home directory.

```bash
ls -a
```
There I saw the file `...Hiding-From-You`

**2. Printing its content to terminal**
A simple `cat` would suffice

```bash
cat ...Hiding-From-You
```
There I saw the password

## 💡 Key Takeaway
Refreshed basic commands.