# PicoCTF: PrivEsc - SUDO MAKE ME A SANDWICH

## 🎯 Objective
Read the `flag.txt` file by finding a way to bypass restricted `sudo` privileges and escalating to the root user.

## 🛠️ Tools & Concepts Used
* `ssh` - protocol used to securely connect to the remote challenge server
* `ls -l` - lists directory contents with detailed information, including file permissions and ownership
* `sudo` - allows a permitted user to execute a command as the superuser (root)
* `sudo -l` - lists the allowed (and forbidden) sudo commands for the current user
* `emacs` - an extensible, customizable text editor
* `Privilege Escalation` - the act of exploiting a bug, design flaw, or configuration oversight to gain elevated access to resources

## 🕳️ Rabbit Holes & Missteps
* **Hypothesis:** Since the challenge is named "SUDO MAKE ME A SANDWICH", simply running `sudo cat flag.txt` will output the flag.
* **Action:** I executed `sudo cat flag.txt` in the terminal.
* **Result:** I received an error: `Sorry, user ctf-player is not allowed to execute '/usr/bin/cat flag.txt' as root on challenge.` The administrators explicitly blocked the `cat` command.

## 📝 Step-by-Step Solution

**0. Understanding the challenge**
After logging into the server via `ssh`, running `ls -l` revealed the `flag.txt` file. The permissions were `-r--r-----`, and it was owned by `root`. As the `ctf-player` user, I had no direct read access to this file. 

**1. Inspect sudo privileges**
Knowing that `cat` was blocked, I needed to figure out what commands I *was* allowed to run. I used the command to list my specific sudo configurations:
```bash
sudo -l
```
**2. Identify the vulnerability**
The output from `sudo -l` returned the following rule at the bottom:

```bash
User ctf-player may run the following commands on challenge:
    (ALL) NOPASSWD: /bin/emacs
```
While the system administrators blocked `cat`, they left the `emacs` text editor completely unrestricted, allowing it to be run as root without requiring a password.

**3. Exploit the allowed command**
Because running a program with sudo grants that specific program root privileges, I could use the text editor to open the file. I ran emacs in the terminal (using -nw to prevent it from trying to open a graphical window):

```Bash
sudo emacs -nw flag.txt
```

**4. Retrieve the flag**
Because `emacs` was now running as the `root` user, it bypassed the file permissions and opened `flag.txt`. The flag was visible right there in the editor. Once copied, I exited the editor using the standard `emacs` shortcut (`Ctrl+X`, then `Ctrl+C`).

**💡 Key Takeaway**
I learned how the `/etc/sudoers`file dictates privilege management in Linux and how to enumerate my own permissions using `sudo -l`. Most importantly, I learned that granting a user `sudo` access to a text editor (like `emacs`, `vim`, or `nano`) is a major security flaw, as it allows for trivial Local Privilege Escalation (LPE) by simply opening restricted files as the root user.