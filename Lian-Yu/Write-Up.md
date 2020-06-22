# Lian-Yu

![image](https://user-images.githubusercontent.com/44063862/83029328-27e9db80-a065-11ea-9c26-76f31a87b355.png)

## Penetration Testing Methodology

**Reconnaissance**
* nmap

**Enumeration**
* Read source code to get another directory

**Exploitation**
* SQL Injection - Login Page
* Command Injection

**Privilege Escalation**
* sudo python

**Capturing the flag**
* /root/root.txt
_______________________________________________________________________________________________________

## Walkthrough

```
nmap <ip>
```



From the nmap scanning. I found that 2 port open. Which is
* 22 (ssh)
* 80 (http)

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

New directory was found. (http://10.10.24.60/island/2100/). There is hint (.ticket). This hint for us to do another dir enumeration for extension .ticket. This time i gonna use gobuster. Gobuster make it easy for me to specify the extension that i need.

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

![image](https://user-images.githubusercontent.com/44063862/83034288-ac8b2880-a06a-11ea-92b1-239a51b84474.png)

I search the header for PNG. To compare with our picture.

![image](https://user-images.githubusercontent.com/44063862/83034399-c75d9d00-a06a-11ea-9c0f-a2e1a58ac8c6.png)

Seems like we have a wrong header. Repair and save. TA_DAA!!

![image](https://user-images.githubusercontent.com/44063862/83034643-0db2fc00-a06b-11ea-9f80-ce1570a71ec4.png)

He, gave us "password". Is it a password for something? Like ssh.... or.. need to be used for other image? Like steghide??? So, I try steghide for both Queen's Gambit.png and aa.jpg. Success for aa.jpg.

```
steghide extract -sf aa.jpg
```

![image](https://user-images.githubusercontent.com/44063862/83035397-faecf700-a06b-11ea-9ba4-962b744d8df0.png)

```
unzip ss.zip
```

![image](https://user-images.githubusercontent.com/44063862/83035453-0e985d80-a06c-11ea-9c05-6e810bad730c.png)

Unzip the file, give us passwd and shado file.

![image](https://user-images.githubusercontent.com/44063862/83035480-19eb8900-a06c-11ea-8e0e-d1848fddb782.png)

```
cat file
```

We get like a password for shado. And "message" from passwd.txt. I felt im on the dead route. If **M3tahuman** is really a password. But, where can we get the username?? 

So, I decide to open ftp again using gftp. I get that there is another user other than vigilante. (/home/vigilante to /home discovered that there is 2 user). Which is slade and vigilante.

![image](https://user-images.githubusercontent.com/44063862/83035976-b3b33600-a06c-11ea-8c50-3dca2f61d5c2.png)

I try to ssh using slade user. With Password: M3tahuman.

![image](https://user-images.githubusercontent.com/44063862/83036080-d04f6e00-a06c-11ea-8e6a-4e84be1bc177.png)

Wahhhhhh, we are in.

![image](https://user-images.githubusercontent.com/44063862/83036114-d9403f80-a06c-11ea-9fd5-183636c53613.png)

**ls** discover user.txt file. Cat file give us first flag.

![image](https://user-images.githubusercontent.com/44063862/83036330-0b51a180-a06d-11ea-9105-4034bd909d09.png)

Next phase is Privilege Escalation

```
sudo -l
```

> To see if there is any command that we can run with root privilege.

![image](https://user-images.githubusercontent.com/44063862/83036417-28867000-a06d-11ea-8596-c9c4f3a0ea98.png)

Seems like, **pkexec** can be run with root privileges. To know more about it we run,

```
man pkexec
```

> pkexec - Execute a command as another user

![image](https://user-images.githubusercontent.com/44063862/83036987-d1cd6600-a06d-11ea-87d2-45dd86e99908.png)

```
sudo pkexec /bin/bash
```

or 

```
sudo /usr/bin/pkexec /bin/bash
```

Successfully change us to root. ls give us root.txt. cat give us our last flag.

![image](https://user-images.githubusercontent.com/44063862/83037039-e27ddc00-a06d-11ea-914d-947c5413b08c.png)

CONGRATULATIONS!! This was a fun machine. Very basic yet fun to root. Good for beginner.

Thank you for reading. :)

**By _AdaniKamal_**
