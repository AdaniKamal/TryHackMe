# Lian-Yu

![image](https://user-images.githubusercontent.com/44063862/83029328-27e9db80-a065-11ea-9c26-76f31a87b355.png)

## Penetration Testing Methodology

**Reconnaissance**
* nmap

**Enumeration**
* Directory Bruteforce using dirbuster & Gobuster

**Privilege Escalation**

**Capturing the flag**
* user.txt
* root.txt
_______________________________________________________________________________________________________

## Walkthrough

```
nmap -A 10.10.24.60
```

![image](https://user-images.githubusercontent.com/44063862/83028953-ae51ed80-a064-11ea-86fe-77fc16022f07.png)

From the nmap scanning. I found that 4 port open. Which is
* 21 (ftp)
* 22 (ssh)
* 80 (http)
* 111 (rpc)

I browse the given IP address.

![image](https://user-images.githubusercontent.com/44063862/83029792-a9da0480-a065-11ea-8d9e-bac1dc0c6f90.png)

But, there is nothing interesting. So, I decide to enumerate the directory. By using dirbuster. (Dirbuster: http://10.10.24.60/)

![image](https://user-images.githubusercontent.com/44063862/83030993-a2672b00-a066-11ea-9434-689fbb0d1148.png)

I get new directory. (http://10.10.24.60/island/) 

![image](https://user-images.githubusercontent.com/44063862/83031121-c62a7100-a066-11ea-820c-64fd8aa326f9.png)

![image](https://user-images.githubusercontent.com/44063862/83031305-fa9e2d00-a066-11ea-8667-36df9b0ce403.png)

There is code word: **vigilante** (not sure for what. So I gonna save it for now.)

I run dirbuster again. (Dirbuster: http://10.10.24.60/island/) because I still dont have any other clue.

![image](https://user-images.githubusercontent.com/44063862/83031552-46e96d00-a067-11ea-9577-d3f7a64afb27.png)

![image](https://user-images.githubusercontent.com/44063862/83031575-4fda3e80-a067-11ea-8c1c-0192dfbce142.png)

New directory was found. (http://10.10.24.60/island/2100/). There is hint (.ticket). This hint for us to do another dir enumeration for extension .ticket.

```
gobuster dir -u 10.10.24.60/island/2100 -w /root/List/directory-list-2.3-medium.txt -x .ticket
```

![image](https://user-images.githubusercontent.com/44063862/83031876-b7908980-a067-11ea-8716-6d9adf7db4c7.png)

Okay, we got successfully got another one. (http://10.10.24.60/island/2100/green_arrow.ticket)

![image](https://user-images.githubusercontent.com/44063862/83032245-2d94f080-a068-11ea-96a4-4d9f42fc49f3.png)

We are given a token **RTy8yhBQdscX**. Seems like this token was encrypt by something. Fire up CyberChef to decrypt our token. After trying, I found that, it was encrypt by Base58.

![image](https://user-images.githubusercontent.com/44063862/83032542-911f1e00-a068-11ea-99fb-3fbe9632c02f.png)

Output: !#th3h00d

So, I think we have got username and password. Maybe for ftp?

```
ftp 10.10.24.60
```

Username: vigilante
Password: !#th3h00d

![image](https://user-images.githubusercontent.com/44063862/83032831-e78c5c80-a068-11ea-8ea3-de672bce3951.png)

Ok, we are in. So, lets dive in. What can we get in here?..

![image](https://user-images.githubusercontent.com/44063862/83033272-7bf6bf00-a069-11ea-97a6-0048224c1d6d.png)

![image](https://user-images.githubusercontent.com/44063862/83033310-86b15400-a069-11ea-895f-ed48e4beabb6.png)

```
ls -al
```

> list all directory or file 

```
get file
```

> download file into our system

So, after ls -al. we can see that, there is 3 image. (Leave_me_alone.png, Queen's Gambit.png and aa.jpg). After download all the file, I try to check each one of it. I have a problem to open Leave_me_alone.png. So, I decide to check the hex using [HxD](https://mh-nexus.de/en/downloads.php?product=HxD20)





**By _AdaniKamal_**
