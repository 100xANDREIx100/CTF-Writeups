# OverTheWire - Bandit - Level 9 -> Level 10

## 🎯 Objective
Find the human readable lines with certain characters in them

## 🛠️ Tools & Concepts Used
* `strings` - displays the printable character sequences that are at least 4 charcters long

## 📝 Step-by-Step Solution

**1. Search for the strings with multiple = in them**
Once logged in, I searched for the few human readable strings, then I pipelined the output to grep in order to pick those with `=` in them

```bash
strings data.txt | grep "==="
```
There, I just got the passoword.

## 💡 Key Takeaway
Refreshed basic commands.