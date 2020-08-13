# Bolt

![image](https://user-images.githubusercontent.com/44063862/90135298-0ddab200-dda5-11ea-866f-ef9a42b1ad00.png)

## :link: Link 

[Bolt](https://tryhackme.com/room/bolt)

## Penetration Testing Methodology

**Reconnaissance**
* nmap

**Exploitation**
* metasploit (bolt cms)

**Capturing the flag**
* flag.txt

_______________________________________________________________________________________________________

## Walkthrough

```
nmap -sV 10.10.54.254
```

![image](https://user-images.githubusercontent.com/44063862/90135425-36fb4280-dda5-11ea-8a40-6b03843ee725.png)

From the nmap scanning. I found that 3 port open. Which is
* 22 (ssh)
* 80 (http)
* 8000 

I browse the given IP address.

![image](https://user-images.githubusercontent.com/44063862/90135540-6316c380-dda5-11ea-8294-c96eb923a1d3.png)

Scroll this page you will get username and password.

![image](https://user-images.githubusercontent.com/44063862/90135755-bb4dc580-dda5-11ea-9752-19d22891802f.png)

![image](https://user-images.githubusercontent.com/44063862/90135857-e33d2900-dda5-11ea-819a-79d770fe4973.png)

But, with this credentials, I still can't access SSH.

So, we find information about this CMS and it's vulnerability. Maybe we can exploit it.

![image](https://user-images.githubusercontent.com/44063862/90136460-c81ee900-dda6-11ea-9b88-373d974bb6b6.png)

Bolt CMS Version.

[Exploit](https://www.exploit-db.com/exploits/48296) that I found. 

![image](https://user-images.githubusercontent.com/44063862/90136640-13d19280-dda7-11ea-8067-29bc92608885.png)

Fire up Metasploit (msfconsole).

![image](https://user-images.githubusercontent.com/44063862/90136793-4e3b2f80-dda7-11ea-950a-aa6a96e41755.png)

show options and set.

![image](https://user-images.githubusercontent.com/44063862/90137040-a2461400-dda7-11ea-958c-d5cd1094d696.png)

![image](https://user-images.githubusercontent.com/44063862/90137151-ce619500-dda7-11ea-9a3a-c08977391aeb.png)

Yesss, root already. Find your flag and grab it :)

![image](https://user-images.githubusercontent.com/44063862/90137276-036de780-dda8-11ea-8b5b-c10334f6b303.png)

CONGRATULATIONS!! This was a fun machine. Very basic yet fun to root. Good for beginner.

Thank you for reading. :)

**By _AdaniKamal_**
