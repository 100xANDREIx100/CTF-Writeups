# OverTheWire - Bandit - Level 13 -> Level 14

## 🎯 Objective
Use a private ssh key to log into the next level

## 🛠️ Tools & Concepts Used
* `ssh` - create a `ssh` connection
* `scp` - secure copy a file from a remote host
* `realpath` - find the absolute path of a file

## 🕳️ Rabbit Holes & Missteps
* **Hypothesis:** Directly ssh-ing from the remote server would solve the challange
* **Action:** I tried to run `ssh` from the server
* **Result:** I was not allwoed to do so

* **Hypothesis:** Directly using the private key would work
* **Action:** I tried to run `ssh` with the key as it was copied
* **Result:** I was not allwoed to do so because it was not secure enough

## 📝 Step-by-Step Solution

**1. Check the current level files**
Once logged in, I checked all the given files in order to find the private key:

```bash
ls -a
```
There I found 2 files : `HINT` and `sshkey.private`. In order to pass this level I needed to use the private key to log into the next one, so I copied it locally:

```bash
scp -P 2220 bandit13@bandit.labs.overthewire.org:/home/bandit13/sshkey.private .
```

**2. Making the key more secure**
In order to be allowed to use it I had to make it only accesible for me

```bash
chmod 600 sshkey.private
```

**3. Log in using the key**
Now I just had to log in

```bash
ssh -i sshkey.private -p 2220 bandit14@bandit.labs.overthewire.org
```
There I found the flag in the specified directory

## 💡 Key Takeaway
Learned how to use ssh with a private key
