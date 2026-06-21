# PicoCTF: Forensics - MyGit

## 🎯 Objective
Get the flag using other identity in git

## 🛠️ Tools & Concepts Used
* `Git` - Core concepts of cloning remote repositories, staging, committing, and pushing changes.

* `git config` - Modifying local Git configuration to spoof or change author identity variables (`user.name` and `user.email`).

* `touch` - A command-line utility used to create a new, empty file.

* `SSH Protocol` - Used to securely connect, authenticate, and clone the remote repository.

## 📝 Step-by-Step Solution

**1. Copy the repo**
First, I had to copy the repo

```bash
git clone ssh://git@foggy-cliff.picoctf.net:53244/git/challenge.git
```
Then I read the `README` file as instructed

**2. Change identity**
Then, I had to change my identity to the required one

```bash
git config user.name "root"
git config user.email "root@picoctf"
```
**3. Create the file and push it**
Then, all left was to create the file and push it

```bash
touch flag.txt
git add flag.txt
git commit "add flag"
git push
```
As a respose I got the flag

## 💡 Key Takeaway
Refreshed basic git commands