# OverTheWire - Bandit - Level 30 -> Level 31

## 🎯 Objective
Retrive a file from a tag

## 🛠️ Tools & Concepts Used
* `git` - distributed control system
* `git tag` - display all tags
* `git show` - display the content of a tag

## 📝 Step-by-Step Solution

**1. Copy the repo**
For this level I had to first copy the repo

```bash
git clone ssh://bandit30-git@bandit.labs.overthewire.org:2220/home/bandit30-git/repo
```
**2. Check all tags**
Then I had to see all the tags

```bash
git tag
```
This displayed a single `secret` tag

**3. Check the content of the tag**
Then I had to check its content

```bash
git show secret
```
## 💡 Key Takeaway
Refreshed `git` use
