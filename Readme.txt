1: The encryption speed must be fast, (need to consider that some are mechanical hard disks, more than 10TB in 3 hours)
2: Each directory needs to create a notepad (notepad content, I can modify it myself)
3: Need to have LAN automatic propagation function (smb protocol. Server with the same rdp password in LAN + 445 port Eternalblue)
4: Need to generate a unique ID in each victim's notepad
5: The decryption private key of each victim needs to be different (each victim has a unique decryptor to prevent victims from spreading to each other)
6: The encryption program and the decryption program need to be generated directly (at least the decryption tool can be generated directly instead of compiling it yourself)
7: Can't be cracked by decryption company (at least 3 months)
8: Can't spread source code to cause flooding
9: Decryption cannot be omitted. If there is any omission, the file can be decrypted separately
10：Encrypt USB device and Shares that can be connected in the network share list

encryption sequence logic：

Exclude the following extensions and directories. Everything else is encrypted
.dll
.exe
.anim
.bat
.bin
.cmd
.hta
.icns
.ico
.ics
.key
.sys

C:\Windows
C:\ProgramData
C:\PerfLogs
C:\Program Files\Intel
C:\Program Files\Google
C:\Program Files\Microsoft
C:\Program Files\Internet Explorer
C:\Program Files\Windows NT
C:\Program Files\WinRAR
C:\Program Files\WindowsPowerShell
C:\Program Files (x86)\Google
C:\Program Files (x86)\Microsoft
C:\Program Files (x86)\Windows Mail
C:\Program Files (x86)\Windows NT
C:\Program Files (x86)\Internet Explorer
C:\Program Files (x86)\WindowsPowerShell

I'm just giving an example
I have not filled in completely, I need to add non-important directories and extensions by myself
---

encryption order:

Important extensions such as .mdf.bak.mdb.dbf.dat.myd.db for databases and .xlsx.docx for documents are encrypted first.

Then encrypt in this order

desktop-D;-E;-F;-C;remaining directory

The program scans the entire disk for extensions and directories. 
Need to be done at the same time as encryption, 
in order to improve efficiency

To complete a directory encryption, you need to generate a notepad from the directory,
Notepad content requirements can be modified （Notepad content is my email address and description）
（If the encryption program is terminated, the directory where the notepad exists will be automatically skipped after restarting, preventing repeated searches and saving time）


Only the header and end files need to be encrypted, 
and the entire file does not need to be encrypted

The above encryption logic is to improve encryption efficiency.
Because you don't know when the server was discovered by the server administrator,
So we need fast encryption

After the encryption is completed, delete the built-in exe file to prevent leakage


unique decryptor：
Requires a different password for each victim
The private key matches the victim key.
Get the password and send it to the victim for decryption


Multi-threaded encryption can be used to improve work efficiency.
encryption speed. Efficiency is very important! ! !



algorithm：RSA4096 and hash 256

The above are just some of my logical ideas and suggestions.
If you can be better, do it your way

If you can do the above, please contact jabber: Satan@0day.im