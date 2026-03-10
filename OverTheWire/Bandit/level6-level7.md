# OverTheWire - Bandit - Level 6 -> Level 7

## 🎯 Objective
Find the file with given propeties on the whole server

## 🛠️ Tools & Concepts Used
* `find` - searches for a file. can be provided extra arguments in order to norrow down the search.

## 🕳️ Rabbit Holes & Missteps
* **Hypothesis:** Just running the find command would be enought
* **Action:** I directly searched for the properties
* **Result:** Checking on the whole server resuled into some errors caused by permission denied so I had to clean the output

## 📝 Step-by-Step Solution

**1. Search for the file with properly configured flags**
Once logged in, I searched for the file using extra flags to find the specific one I need. I also had to throw away the error messages because `access denined` on a files would be of no help to me.

```bash
find / -size 33c -group bandit6 -user bandit7 2> /dev/null
```
There I just got one file which I readed.

## 💡 Key Takeaway
I learened how to throw away erorrs