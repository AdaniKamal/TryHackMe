# Wonderland

![image](https://user-images.githubusercontent.com/44063862/84010737-aa4c9680-a9a7-11ea-9e26-84cae1ec7f5c.png)

## Penetration Testing Methodology

**Reconnaissance**

* nmap

**Enumeration**

* Directory Bruteforce using dirbuster & Gobuster

**Exploitation**

* 

**Privilege Escalation**

* 

**Capturing the flag**

* user.txt
* root.txt

--------------------------------------------------------------------------------------------------------------------------

## Walkthrough - There is so many rabbit hole. Watch out.

1) nmap - to find open port

```
nmap -A 10.10.177.100
```

2) enumerate directory (**Gobuster** // **Dirbuster**)

```
gobuster dir -u http://10.10.177.100/ -w /root/List/directory-list-2.3-medium.txt -t 80 -x .txt,.php,.html
```

or 

```
dirbuster
```

-> We can use any Gobuster or Dirbuster. But for this machine I recommend use dirbuster. It will make your task easier.

**First**

![image](https://user-images.githubusercontent.com/44063862/84012107-a4f04b80-a9a9-11ea-83cd-36ad2bd4f831.png)

**Second**

![image](https://user-images.githubusercontent.com/44063862/84012190-c2bdb080-a9a9-11ea-9bd1-4e7a2d6f8a62.png)

**Third**

![image](https://user-images.githubusercontent.com/44063862/84013075-0369f980-a9ab-11ea-8da8-8e0477e9fa03.png)

**Fourth**

![image](https://user-images.githubusercontent.com/44063862/84012973-e7665800-a9aa-11ea-9791-6917ccb1fc65.png)

**Fifth**

![image](https://user-images.githubusercontent.com/44063862/84013124-17156000-a9ab-11ea-8548-d0e900b8705a.png)

**Sixth**

![image](https://user-images.githubusercontent.com/44063862/84013165-27c5d600-a9ab-11ea-84a0-2f018219b6e6.png)

**Seventh**

![image](https://user-images.githubusercontent.com/44063862/84013231-3ad8a600-a9ab-11ea-88d8-f1b90f624bb8.png)

3) ssh

```
ssh *****@10.10.177.100
```

```
ls -al
```

Oops, there is root.txt. But we can't opened it. 

![image](https://user-images.githubusercontent.com/44063862/84032573-222bb880-a9ca-11ea-8456-353bb295ee8e.png)

Here, where the hint is really useful. 

![image](https://user-images.githubusercontent.com/44063862/84032644-3cfe2d00-a9ca-11ea-9ccb-96fd7a6e660f.png)

okay the, we try a usual place for root.txt.

```
cat /root/user.txt
```

![image](https://user-images.githubusercontent.com/44063862/84033048-db8a8e00-a9ca-11ea-9b79-797f088fc9d7.png)

Well, that was an easy guess I think.

Now, the root flag.

**By _Adanikamal_**
