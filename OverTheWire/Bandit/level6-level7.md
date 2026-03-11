# OverTheWire - Bandit - Level 6 -> Level 7

## 🎯 Objective
Find the file with given properties on the whole server

## 🛠️ Tools & Concepts Used
* `find` - searches for a file. can be provided extra arguments in order to narrow down the search.

## 🕳️ Rabbit Holes & Missteps
* **Hypothesis:** Just running the find command would be enough
* **Action:** I directly searched for the properties
* **Result:** Checking on the whole server resulted into some errors caused by permission denied so I had to clean the output

## 📝 Step-by-Step Solution

**1. Search for the file with properly configured flags**
Once logged in, I searched for the file using extra flags to find the specific one I needed. I also had to throw away the error messages because `access denied` on a file would be of no help to me.

```bash
find / -size 33c -group bandit6 -user bandit7 2> /dev/null
```
There, I just got one file which I read.

## 💡 Key Takeaway
I learned how to throw away errors