# SSS: Forensics - Operation 1337 Niffer

## 🎯 Objective
Find the flag in the pcap file

## 🛠️ Tools & Concepts Used
* `pcap` - Packet Capture file - stores captured network traffic
* `wireshark` - network protocol analyzer

## 🕳️ Rabbit Holes & Missteps
* **Hypothesis:** The flag is in some packet somewhere
* **Action:** I tried to applay a display filter, namely `frame contains "SSS{"`
* **Result:** No packet displayed

## 📝 Step-by-Step Solution

**1. Open the file into Wireshark**
First, I opened the file into Wireshark

**2. Extract the HTTP objects**
Then, I extracted all the  HTTP objects locally

**3. Unarchive the files**
Then, I found a tar.gz file that I unarchied.

```bash
tar -xzvf 08347211akamai.tar.gz 
```

There I found the `flag.txt` file that had the flag inside, namely `SSS{prind_pachete_pe_retea}`

## 💡 Key Takeaway
I learned how to extract objects from a pcap file.