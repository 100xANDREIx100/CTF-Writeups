# OverTheWire - Bandit - Level 17 -> Level 18

## 🎯 Objective
Find the password using `diff`

## 🛠️ Tools & Concepts Used
* `diff` - find the differences between 2 files

## 📝 Step-by-Step Solution

**1. Find the differences**
Once logged in, I run the `diff` utilitary on the specified files

```bash
diff passwords.old  passwords.new
```
The output was the password for the next level

## 💡 Key Takeaway
Refreshed the use of `diff`
