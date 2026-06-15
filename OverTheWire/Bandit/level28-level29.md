# OverTheWire - Bandit - Level 28 -> Level 29

## 🎯 Objective
Retrive an old version of a `git` file

## 🛠️ Tools & Concepts Used
* `git` - distributed control system
* `git show` - display an old version of a git file
* `git log` - display all the previous versions of a file

## 📝 Step-by-Step Solution

**1. Copy the repo**
For this level I had to first copy the repo

```bash
git clone ssh://bandit28-git@bandit.labs.overthewire.org:2220/home/bandit28-git/repo
```
**2. Check old versions**
Then I had to see all the old versions

```bash
git log --oneline
```
This displayed a total of 3 versions out of which I picked the oldest to display

**3. See the content of the oldest**
Then I just had to read the oldest one

```bash
git show 0ac73ca
```
## 💡 Key Takeaway
Refreshed `git` use
