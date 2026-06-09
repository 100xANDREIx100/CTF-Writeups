# OverTheWire - Bandit - Level 22 -> Level 23

## 🎯 Objective
Recreate the logic of a bash script

## 🛠️ Tools & Concepts Used
* `cron` - time based job scheduler 
* `bash` - interactive command interpreter and command language 

## 📝 Step-by-Step Solution

**1. Look at the configuration**
I had to first look into the configuration of `cron`

```bash
cd ../../etc/cron.d
```
In this directory there was a file named `cronjob_bandit23`, which I simply read

```bash
cat cronjob_bandit23
```

**2. Run the programmed command**
Then, I read the file I found

```bash
cat ../../usr/bin/cronjob_bandit23.sh
```
It outputed the way that the password for `bandit22` was copied into a `tmp` folder, so I just had to recreate it for `bandit23`

**3. Recreate the command**
Then, I had to execute the command for the next level
```bash
echo I am user bandit23 | md5sum | cut -d ' ' -f 1
```

It just outputed name of the file where I could find the password

**4. Read the file**
Then, all left was to read that mysterious files 

```bash
cat ../../tmp/8ca319486bfbbc3663ea0fbe81326349
```

It just outputed the password for the next level 

## 💡 Key Takeaway
Practiced script interpretation and reproduction
