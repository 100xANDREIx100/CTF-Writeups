# PicoCTF: Cryptography - hashcrack

## 🎯 Objective
Find the flag in the provided server

## 🛠️ Tools & Concepts Used
* `nc` - reads and writes data across a network connection
* `https://hashes.com/en/decrypt/hash` - search for a specific common hash and cracks it (if found)
* `MD5 hash` - widely used hash algorithm - 128 bit value
* `SHA1 hash` - usually produces a 40 digit hexadecimal number- 160 bit value
* `SHA256 hash` - deterministic, one-way, collision resistant - 256 bit value
## 📝 Step-by-Step Solution

**1. Connection to the server**
First, I connected to the server using the provided command

```bash
nc verbal-sleep.picoctf.net 59963
```

**2. Cracking the hashes**
Then, I was provided with a hash, which I copied and cracked it. This process repeated 3 times, after each pasting the cracked message I was shown with a new one, in the end being the flag.

## 💡 Key Takeaway
I learned about the existence of multiple hash algorithms and their properties and I also added to my personal toolkit a pretty useful hash cracker.