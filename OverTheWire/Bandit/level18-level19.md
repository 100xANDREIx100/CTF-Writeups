# OverTheWire - Bandit - Level 18 -> Level 19

## 🎯 Objective
Find the password bypassing the `.bashrc` file

## 🛠️ Tools & Concepts Used
* `ssh` - network protocol for operating remote machines

## 📝 Step-by-Step Solution

**1. Log in bypassing the broken file**
To bypass the `.bashrc` ffile I had to provide the `cat reeadme` file as an argument of `ssh`, as it will be executed before the first load of `.bashrc`

```bash
ssh -p 2220 -l bandit18 bandit.labs.overthewire.org "cat readme"
```
The output was the password for the next level

## 💡 Key Takeaway
Learned how to bypass the initial load of `.bashrc`
