# OverTheWire - Bandit - Level 21 -> Level 22

## 🎯 Objective
Find the command `cron` is running regularly

## 🛠️ Tools & Concepts Used
* `cron` - time based job scheduler 

## 📝 Step-by-Step Solution

**1. Look at the configuration**
I had to first look into the configuration of `cron`

```bash
cd ../../etc/cron.d
```
In this directory there was a file named `cronjob_bandit22`, which I simply read

```bash
cat cronjob_bandit22
```

**2. Run the programmed command**
Then, I ran the command I found

```bash
bash ../../usr/bin/cronjob_bandit22.sh
```
It outputed that it cannot change the permissions of a file found in `tmp`

**3. Read the file**
Then, all left was to read that mysterious files 

```bash
cat ../../tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
```

It just outputed the password for the next level 

## 💡 Key Takeaway
Learned about `cron`
