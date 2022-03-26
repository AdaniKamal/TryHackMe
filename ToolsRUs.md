# ToolsRUs

IP: 10.10.154.123

### Penetration Testing Methodology

![image](https://user-images.githubusercontent.com/44063862/160220590-db70b7dd-a85c-407f-b5d8-e42e9fa58dc3.png)

**Reconnasance**
* nmap

**Enumerating**
*

**Exploitation**
*

**Privilege Escalation**
*

**Capture-the-flag**
* user.txt
* root.txt

----------------------------------------------------------------
### Walkthrough

> nmap -A -v 10.10.154.123

![image](https://user-images.githubusercontent.com/44063862/160220987-1488e56b-495e-432b-b918-d18d0210edca.png)

From the nmap scanning. I found that 4 port open. Which is

* 22 (ssh)
* 80 (http)
* 1234 (http)
* 8009 (ajp13)

> gobuster dir -u 10.10.154.123 -w /root/Lists/directory-list-2.3-medium.txt

![image](https://user-images.githubusercontent.com/44063862/160221188-392ad5e9-feee-40ae-a7b8-10ae513d9ca2.png)

/guidelines
/protected

![image](https://user-images.githubusercontent.com/44063862/160221062-7041cfd6-1a21-43a5-ab6f-fecdf772b4f1.png)

--> msg for Bob 

![image](https://user-images.githubusercontent.com/44063862/160221118-9f0c0a30-8719-4f27-8898-9158da18f847.png)

--> need authentication

