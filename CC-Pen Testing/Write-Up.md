# CC - Pen Testing

## Methodology:

**Scanning/Reconnaisance**
   * nmap →  nmap -A 10.10.51.180
   
**Enumeration**
  * Gobuster/Dirbuster

**Exploitation**
  * Hashcat → hashcat --force -m 1800 <hash> /root/List/rockyou.txt --session sha512

**Privilege Escalation**
  * sudo -l

**Capturing the flag**
* user.txt
* root.txt

______________________________________________________________________________________________________________________________________

## Walkthrough

### NMAP

First, we do nmap the IP. From the result there is only 2 port open. (22 & 80)

```
nmap -A 10.10.51.180
```

![image](https://user-images.githubusercontent.com/44063862/83943783-31c3c980-a831-11ea-8893-ee4626d0d68c.png)

### Gobuster

Open, port 80 on web, there is only page apache. Maybe we need to dirb. But, I prefer gobuster.

```
gobuster dir -u http://10.10.51.180/ -w /root/List/directory-list-2.3-medium.txt -t 80 -x .txt,.php,.html
```

Well, the directory that we found giving us a blank page. Dirb again as /secret is (301) which means a directory.

```
gobuster dir -u http://10.10.51.180/secret/ -w /root/List/directory-list-2.3-medium.txt -t 80 -x .txt,.php,.html
```

![image](https://user-images.githubusercontent.com/44063862/83943996-ef02f100-a832-11ea-8fe4-ccbe8b72cc06.png)

### Hashcat

Well, what hash is this? Check it through [Hash Analyzer](https://www.tunnelsup.com/hash-analyzer/)

Next, after found out the hash type, we need to find out the hash mode. 

I suggest this website. [Hash](https://hashcat.net/wiki/doku.php?id=example_hashes)

```
hashcat --force -m 100 046385855FC9580393853D8E81F240B66FE9A7B8 /root/List/rockyou.txt --session SHA1
```

![image](https://user-images.githubusercontent.com/44063862/83944022-1f4a8f80-a833-11ea-992a-c1d426be7cd1.png)

### Privilege Escalation

```
ssh nyan@10.10.51.180
```

![image](https://user-images.githubusercontent.com/44063862/83944050-4acd7a00-a833-11ea-9179-adf52e8c4b93.png)

```
sudo -l
```

![image](https://user-images.githubusercontent.com/44063862/83944066-5faa0d80-a833-11ea-87d4-a004556a3753.png)

![image](https://user-images.githubusercontent.com/44063862/83944383-ad277a00-a835-11ea-90ac-71b829e16ea5.png)


CONGRATULATIONS, we got the flag.

**By _AdaniKamal_**






















