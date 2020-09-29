# RootMe

![image](https://user-images.githubusercontent.com/44063862/94501784-3b849900-0235-11eb-924c-f15926a6864e.png)

## Penetration Testing Methodology

**Reconnaissance**
* nmap

**Enumeration**
* Directory enumeration using gobuster and dirbuster

**Exploitation**
* 

**Privilege Escalation**
* 

**Capturing the flag**
* user.txt
* root.txt
_______________________________________________________________________________________________________

## Walkthrough

```
nmap -sC -sV 10.10.231.227
```

![image](https://user-images.githubusercontent.com/44063862/85245613-baba4200-b47a-11ea-8e23-7cda437d5fcd.png)

From the nmap scanning. I found that 2 port open. Which is
* 22 (ssh)
* 80 (http)

I browse the given IP address.

![image](https://user-images.githubusercontent.com/44063862/94501885-6838b080-0235-11eb-8aa9-bce47bb4f992.png)

But, there is nothing interesting. So, I decide to enumerate the directory. By using dirbuster.


```
ls -al
```

> list all directory or file 


CONGRATULATIONS!! This was a fun machine. Very basic yet fun to root. Good for beginner.

Thank you for reading. :)

**By _AdaniKamal_**

