# OverTheWire - Bandit - Level 32 -> Level 33

## 🎯 Objective
Escape the shell

## 🛠️ Tools & Concepts Used
* `$0` special variable that holds the name of the current process

## 📝 Step-by-Step Solution

**1. Test the functionality**
For this level I had to first see what the shell actually does

```bash
ls
cat
LS
echo 012
ls .
0123
```

This way I observed that all lowercase letters are transformed into uppercase ones, but nothing changes to special characters or numbers, so then I tried with them

**2. See current process**
The solution of this level was simply to call `$0`

```bash
$0
```
This made me escape the shell

**3. Get the password for the next level**
Then I just had to get the next password

```bash
cat /etc/bandit_pass/bandit33
```

And there it displayed the password for the next level

## 💡 Key Takeaway
Practiced lateral thinking
