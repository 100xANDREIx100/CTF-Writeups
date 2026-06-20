# PicoCTF: Cryptography - undo

## 🎯 Objective
Apply changes to the string

## 🛠️ Tools & Concepts Used
* `nc` - reads and writes data across a network connection
* `base64`: A command-line utility used to encode and decode data into a standard ASCII text format.
* `rev`: A Linux command that reverses the order of characters in a given string of text.
* `tr` (Translate): A versatile text-processing command used to swap, substitute, or delete specific characters.
* `ROT13 Cipher`: A foundational substitution cipher (and a subset of the Caesar cipher) that replaces a letter with the 13th letter after it in the alphabet.
* `Data Pipelining / CLI Text Manipulation`: The core concept of sequentially passing and transforming text outputs through multiple command-line utilities to reveal a hidden flag.

## 📝 Step-by-Step Solution

**1. Connection to the server**
First, I connected to the server using the provided command

```bash
nc foggy-cliff.picoctf.net 49277
```

**2. Decode from base64**
Then, I has to decode from base64

```bash
base64 -d
```

**3. Reverse the text**
Then, I had to reverse it

```bash
rev
```

**4. Change certain characters**
Then, I had to change `-` with `_`

```bash
tr '-' '_'
```

And then `()` with `{}`

```bash
tr '()' '{}'
```
**5. Apply ROT13 to it**
Then, I had to rotate 13 characters back

```bash
tr 'a-zA-Z' 'n-za-mN-ZA-M'
```


## 💡 Key Takeaway
I refreshed some basic linux commands