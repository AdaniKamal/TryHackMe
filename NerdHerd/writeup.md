# NerdHerd

## :link: Link 
[Bolt]()

## Penetration Testing Methodology

**Reconnaissance**
* nmap

**Exploitation**
*

**Capturing the flag**
* 
_______________________________________________________________________________________________________

## Walkthrough

```
nmap -sC -sV -p- -vv 10.10.133.57
```

Port open --> 21, 22, 139, 445, 1337

## Web Enumeration

Browse the IP. there is a link. The link: https://www.youtube.com/watch?v=9Gc4QTqslN4

```
gobuster dir -u http://10.10.133.57:1337 -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
```

Output: /admin

Browse it. And look at the page source. There is Y2liYXJ0b3dza2k= : aGVoZWdvdTwdasddHlvdQ==

So we decode using Cyber Chef. 

Y2liYXJ0b3dza2k= is cibartowski

Another one is invalid.

```
ftp 10.10.133.57
```

Login as anonymous. And we get youfoundme.png. Analyse it.

```
exiftool youfoundme.png
```
Something fishy about "Owner name: fijbxslz"

Another file is hellon3rd.txt

```
cat hellon3rd.txt
```
Output: all you need is in the leet

Cipher identifier: https://www.boxentriq.com/code-breaking/cipher-identifier
Output: Vigenere Cipher.


After try a lot, I found that the key is **birdistheword** from the youtube link.

Decode the vigenere key get easypass.

I use this as a SMB password.

## SMB Enumeration

```
smbclient -L 10.10.137.57
```
Sharename: nerdherd_classified

```
enum4linux 10.10.133.57
```
username: chuck

```
smbclient -U chuck \\\\10.10.133.57\\nerdherd_classified
```
pw: easypass

Will get secr3t.txt. Which contain /this1sn0tadirect0ry

Which will auto to page --> http://10.10.133.57:1337/this1sn0tadirect0ry/c****.t**

Where contains Credential for SSH.

## SSH

```
ssh *****@10.10.133.57
```

User cannot run sudo (sudo -l)

So, we check 

```uname -a``` - To check kernel vulnerability

https://www.exploit-db.com/exploits/45010

Kernel exploits are written in C, which are compiled using gcc. 

First let's check if the victim machine have gcc

I copy the exploit code into the victim system.

```
nano 45010.c
```

Now compile it using gcc and give permission to run using chmod

Okay now we can run the exploit.

Poof!! root.

```
locate root.txt
```

CONGRATULATIONS!! This was a fun machine.

Thank you for reading. :)

**By _AdaniKamal_**
