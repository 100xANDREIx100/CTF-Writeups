# OverTheWire - Bandit - Level 8 -> Level 9

## 🎯 Objective
Find the lie repeted only once in a file

## 🛠️ Tools & Concepts Used
* `sort` - print the output of a file in given order
* `uniq` - detect duplicates

## 📝 Step-by-Step Solution

**1. Search for the unique string in a file**
Once logged in, I searched for the unique string in the provided file.

```bash
sort data.txt | uniq -u
```
There I just got one string which was the password.

## 💡 Key Takeaway
I learened how to operate with with `sort` and `unique`