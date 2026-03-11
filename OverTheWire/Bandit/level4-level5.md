# OverTheWire - Bandit - Level 4 -> Level 5

## 🎯 Objective
Find the password in the human readable file

## 🛠️ Tools & Concepts Used
* `file` - specifies the type of the file

## 📝 Step-by-Step Solution

**1. Enter and list all files**
Once logged in, I entered the directory and listed all files inside

```bash
cd inhere/
ls
```
There I saw 10 files with names from `-file00` to `-file09`

**2. Checking each file type and reading the right one**
On each of them I run the same command in order to find the one with human readable data.

```bash
file "./-file00"
```
There I saw that all were `data` files except for one which was `ASCII text`. I read that one (with `cat`).

## 💡 Key Takeaway
Refreshed basic commands.