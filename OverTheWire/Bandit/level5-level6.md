# OverTheWire - Bandit - Level 5 -> Level 6

## 🎯 Objective
Find the file with given propeties in the given folder

## 🛠️ Tools & Concepts Used
* `find` - searches for a file. can be provided extra arguments in order to norrow down the search.

## 📝 Step-by-Step Solution

**1. Enter and list all files**
Once logged in, I searched for the file using extra flags to find the specific one I need

```bash
find . -type f -size 1033c ! -executable
```
There I just got one file which I readed.

## 💡 Key Takeaway
Refreshed basic commands.