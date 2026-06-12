# OverTheWire - Bandit - Level 25 -> Level 26

## 🎯 Objective
Escape the terminal

## 🛠️ Tools & Concepts Used
* `more` - view the content of a large file
* `bash` - interactive command interpreter and command language outputed
* `shell` - interprets and executes commands
* `vim` - (best) text editor

## 📝 Step-by-Step Solution

**1. Find the current shell**
First I had to read the shell of the next level

In order to do that I first found the file:

```bash
#!/usr/bin/env bash
getent passwd | awk -F: '{print $1, "=>", $7}'
```
This displayed all shells for all users, here I found the shell of `bandit26` and then I read it

```bash
#!/usr/bin/env bash
cat usr/bin/showtext
```

**2. Exploit the vulnerability**
Then, I had to exploit the `more` command by making my terminal extremely small and connecting to the next level (using the provided key) so it had to display in the just a part of the content

```bash
ssh -p 2220 -i bandit26.sshkey bandit26@bandit.labs.overthewire.org
```

Here, I pressed `v` in order to get into `vim` and there I executed

```bash
:set shell=/bin/bash
```
and

```bash
:shell
```

This way I escaped into the classic bandit environment

P.S. For logging with the provided sshkey see the writeup for `level13-level14`.

## 💡 Key Takeaway
Learned how to exploit the `more` command
