# Anonforce 

![image](https://user-images.githubusercontent.com/44063862/83507421-1be59a00-a4fb-11ea-990c-20acc14ecfff.png)

**https://tryhackme.com/room/bsidesgtanonforce**

## Steps:

1) nmap
2) ftp
- login anonymous
- User.txt (ftp://10.10.30.141/home/melodias/user.txt)
3) Look at all file
- notread file interesting
- Got 2 file (pgp and asc)
4) Decrypt pgp
- need password for asc file
- use john
5) Get list of user and password
- Interested (root)
- hashcat root 
- root: hikari
6) ssh
- ssh root@10.10.239.40
- ls -al
- cat root.txt

Download my CherryTree notes for more beautiful and detail walkthrough. [Anonforce.ctb](https://github.com/AdaniKamal/TryHackMe/blob/master/Anonforce/Anonforce.ctb)

**By _AdaniKamal_**
