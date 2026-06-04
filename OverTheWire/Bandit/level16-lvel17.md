# OverTheWire - Bandit - Level 16 -> Level 17

## 🎯 Objective
Find the specified port

## 🛠️ Tools & Concepts Used
* `nmap` - open source utility for port scanning
* `openssl` - use OpenSSL cryptography library

## 🕳️ Rabbit Holes & Missteps
* **Hypothesis:** Using `netstat` would find the required port
* **Action:** I tried to run `netstat -tuln`
* **Result:** Netstat only listed IPV6 ports, out of which none was the right one

* **Hypothesis:** Directlly connecting on the right port would do
* **Action:** I tried to run `openssl s_client -connect localhost:31960`
* **Result:** When pasting the key I kept getting `KEYUPDATE` because the key started witk `k`


## 📝 Step-by-Step Solution

**1. Enumerate all ports**
Once logged in, I enumerated all listening ports in the specified range

```bash
nmap -p 31000-32000 localhost
```

**2. Find the right one**
Then, I tried to connect via SSL on all listed ports

```bash
openssl s_client -connect localhost:31960
```
All of them (minus 1) outputed error messages.

**3. Retrieve the flag**
I had to connect to the right port using `-quiet` flag, since the password I had to provide started with `k` and was initially considered a `KEYUPDATE` message

```bash
openssl s_client -connect localhost:31790 -quiet
```

There I got the RSA key for the next level

## 💡 Key Takeaway
Learned how to use `nmap` and `-quiet` flag of `openssl`
