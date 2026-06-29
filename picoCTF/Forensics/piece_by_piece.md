# PicoCTF: Forensics - Piece By Piece

## 🎯 Objective
Get the flag by combining files

## 🛠️ Tools & Concepts Used
* `cat` - display file content
* `touch` - create a file
* `unzip` - unzip a file

## 📝 Step-by-Step Solution

**1. Concatenate all files**
First, I had to create a file and then concatenate all parts together
```bash
touch fin
cat part_aa >> fin 
cat part_ab >> fin 
cat part_ac >> fin 
cat part_ad >> fin 
cat part_ae >> fin 
```

**2. Unzip**
Then, I had to unzip the result

```bash
unzip fin
```
**3. Unlock the result**
Then, all left was to insert the `supersecret` password

```bash
supersecret
```
As a respose I got the file with the flag

## 💡 Key Takeaway
Refresh basic forensics methods