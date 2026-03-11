# OverTheWire - Bandit - Level 5 -> Level 6

## 🎯 Objective
Find the file with given properties in the given folder

## 🛠️ Tools & Concepts Used
* `find` - searches for a file. Can be provided extra arguments in order to narrow down the search.

## 📝 Step-by-Step Solution

**1. Search for the specific file**
Once logged in, I searched for the file using extra flags to find the specific one I needed

```bash
find . -type f -size 1033c ! -executable
```
There, I just got one file which I read.

## 💡 Key Takeaway
Refreshed basic commands.