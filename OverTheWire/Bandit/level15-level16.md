# OverTheWire - Bandit - Level 15 -> Level 16

## 🎯 Objective
Communicate sung SSL/TSL encryption

## 🛠️ Tools & Concepts Used
* `openssl` - use OpenSSL cryptography library

## 📝 Step-by-Step Solution

**1. Connect to localhost**
Once logged in, I connected to localhost on the required port, sung the required connection type

```bash
openssl s_client -connect localhost:30001
```

`s_client` - act as a generic client
`-connect localhost:30001` connect to the specified interface and port 

**2. Sending the password**
There, I just had to send the previous password without anything extra

## 💡 Key Takeaway
Learned how to use `openssl` in order to connect toa specieid port of an interface via SSL
