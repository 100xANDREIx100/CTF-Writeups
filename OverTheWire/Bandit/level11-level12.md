# OverTheWire - Bandit - Level 11 -> Level 12

## 🎯 Objective
Decode the ROT13 file

## 🛠️ Tools & Concepts Used
* `tr` - provided with two sets of characets it translates from the first one to the second one
## 📝 Step-by-Step Solution

**1. Decode the file**
Once logged in, I decoded the file by pipieling the content of the file to the `tr` command followed by the classic alphtabet `a-zA-Z` and the rotated one `n-za-mN-ZA-M`in order to obtain the decoded message

```bash
cat data.txt | tr 'a-zA-Z' 'n-za-mN-ZA-M'
```
There, I just got the passoword.

## 💡 Key Takeaway
Learned how to use the `tr` command