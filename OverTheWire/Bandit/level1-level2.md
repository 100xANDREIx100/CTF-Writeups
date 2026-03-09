# OverTheWire - Bandit - Level 1 -> Level 2

## 🎯 Objective
Find the password in the `-` file

## 🛠️ Tools & Concepts Used
* `realpath` - prints the absolute path of a file
* `cat` - write the content of a file to standard output

## 📝 Step-by-Step Solution

**1. List all files in current directory**
Once logged in, I needed to see what files were available in the home directory.

```bash
ls
```
There I saw the file `-`

**2. Getting the abouslte path**
Knowing that on such tricky files a simple cat will not work, I searched for the abolute path of the file

```bash
realpath -
```

**3. Read its content**
Then I printed its content in the terminal

```bash
cat /home/bandit1/-
```
There I saw the password

## 💡 Key Takeaway
Refreshed basic commands.