# OverTheWire - Bandit - Level 31 -> Level 32

## 🎯 Objective
Push to a git repository

## 🛠️ Tools & Concepts Used
* `git` - distributed control system
* `git push` - push to a remote repository
* `git add` - stage files
* `git commit` - commit the made changes

## 📝 Step-by-Step Solution

**1. Copy the repo**
For this level I had to first copy the repo

```bash
git clone ssh://bandit31-git@bandit.labs.overthewire.org:2220/home/bandit31-git/repo
```
**2. Create the specified file**
Then I had to create a file named `key.txt` with the content `May I come in?`

```bash
vim key.txt
```

**3. Push the file**
Then I just had to push it

```bash
git add -f key.txt
git commit "text"
git push 
```

And there it displayed the password for the next level

## 💡 Key Takeaway
Refreshed `git` use
