# OverTheWire - Bandit - Level 12 -> Level 13

## 🎯 Objective
Decompress the file multiple times until the password is found

## 🛠️ Tools & Concepts Used
* `file` - displays the type of tile
* `mv` - moves a file, but also renames it
* `mktemp -d` - make a temporary file or directory with an unique name
* `cp` - copies data from a folder to another
* `xxd -r` - with the specified flag, it retuns a hexdump file back into binary
* `gzip -d` - decompresses a gzip compressed file
* `bzip2 -d` - decompresses a bzip2 compressed file
* `tar  -xf` - extracts the content from a file

## 📝 Step-by-Step Solution

**1. Prepare the workspace**
Once logged in, I knew I had to work with a file more than just reading it, and since I had only reading permission in the home directory, I created a temporary directory with an unique name and copied the file there so I can work freely on it

```bash
mktemp -d // this command outputed to me /tmp/tmp.d1IVONmkqn
cp data.txt /tmp/tmp.d1IVONmkqn
```
**2. Reversing the hexdump**
A hexdump file would be of no use, so I reverted it back to binary in order to be able to decompress it.

```bash
xxd -r data.txt > file1
```

**3. Decompressing the file**
Now I just had to decompress the file, but I did not know which compressing algorithm was used, so I found out with the `file` command 

```bash
file file1 
file1: gzip compressed data
```
Being compressed with `gzip` means that I had to use the same algorithm in order to decompress it. In order to do this I had to rename the file for it to have the proper extension so it can be recognized and therefore decompressed.

```bash
mv file1 file1.gz
```

Now, I could just decompress it

```bash
gzip -d file1.gz
```
Here I tought the work is done, but printing the file to the terminal enlisted a bunch of non-ASCII characters, so I went to the same process as before:

```bash
file file1
file1: bzip2 compressed data
```

Different algorithm, same principle: change the name of the file and decompress it.

```bash
mv file1 file1.bz
bzip2 -d file1.bz
```
After this step, the new file was again compressed with `gzip`, but after that one I got something new:

```bash
file file1 
file1: POSIX tar archive (GNU)
```
This one does not need a special extension, so I directly extracted the file from it:

```bash
tar -xf file1
```
From this step onwards, each decompressed file was still compressed in one of the 3 formats enumerated above, so for each I used the `file` command to identify the compression algorithm and then applied the specific one until the end where the last file was just an `ASCII` file which I simply printed to the terminal using `cat`

## 💡 Key Takeaway
Learned 2 methods of compression (`gzip`, `bzip2`), one of bundeling multipe files into one (`tar`) and how to treat `hexdump` files (specifically how to go to and from `binary`)