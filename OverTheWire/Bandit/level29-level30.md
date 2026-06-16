# OverTheWire - Bandit - Level 28 -> Level 29

## 🎯 Objective
Retrive a file from a branch

## 🛠️ Tools & Concepts Used
* `git` - distributed control system
* `git branch -a` - display all branches
* `git checkout` - change branch

## 📝 Step-by-Step Solution

**1. Copy the repo**
For this level I had to first copy the repo

```bash
git clone ssh://bandit29-git@bandit.labs.overthewire.org:2220/home/bandit29-git/repo
```
**2. Check all branches*
Then I had to see all the branches

```bash
git branch -a
```
This displayed a total of 3 branches which I had to check

**3. Go to the first**
Then I had to check each branche's `README.md` file

```bash
git checkout dev
cat README.md 
```
## 💡 Key Takeaway
Refreshed `git` use
