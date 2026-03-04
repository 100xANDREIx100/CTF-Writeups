# PicoCTF: Forensics - DISKO 1

## 🎯 Objective
Find the flag in the provided disk image.

## 🛠️ Tools & Concepts Used
* `strings` - find the printable strings in a binary file.
* `grep` - search for a specific pattern of characters.
* `gunzip` - decompress files.

## 📝 Step-by-Step Solution

**1. Decompressing the file:**
First, I searched online to figure out what the extension was, since it was the first time I saw `.dd.gz` at the end of a file. It turned out to be a compressed file (`.gz`) of a raw disk image (`.dd`). The compression was made using gzip, so I used the `gunzip` program in order to decompress it.

```bash
gunzip disko1.dd.gz
```

**2. Finding the strings:**
Then, I extracted the human-readable text from the disk image using the `strings` command. I fed (piped) this output into the `grep` command to search exactly for `picoCTF`, which is the standard format of the flag, successfully finding it this way.

```bash
strings disko1.dd | grep picoCTF
```

## 💡 Key Takeaway
I learned how to identify and extract data from compressed disk images (`.gz` / `.dd`) and how to use terminal pipes (`|`) to efficiently chain commands together to filter through large amounts of data.