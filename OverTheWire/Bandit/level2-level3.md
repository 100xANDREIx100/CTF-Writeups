# OverTheWire - Bandit - Level 2 -> Level 3

## 🎯 Objective
Find the password in the `--spaces in this filename--` file

## 🛠️ Tools & Concepts Used
* `cat` - write the content of a file to standard output

## 📝 Step-by-Step Solution

**1. List all files in current directory**
Once logged in, I needed to see what files were available in the home directory.

```bash
ls
```
There I saw the file `--spaces in this filename--`

**2. Printing its content to terminal**
Knowing that a simple `cat` will not work on such tricky files, I wrapped the filename in quotes "" and used the relative path trick `./.`

```bash
cat "./--spaces in this filename--"
```
There, I saw the password.

## 💡 Key Takeaway
Refreshed basic commands.