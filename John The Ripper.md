# John The Ripper

### Task 4 Cracking Basic Hashes

Use:
```
https://www.tunnelsup.com/hash-analyzer/
https://crackstation.net/
```

### Task 5 Cracking Windows Authentication Hashes

Use:
```
https://www.tunnelsup.com/hash-analyzer/
https://crackstation.net/
```

### Task 6 Cracking /etc/shadow Hashes

**Unshadowing process**

unshadow [path to passwd] [path to shadow]

unshadow - Invokes the unshadow tool
[path to passwd] - The file that contains the copy of the /etc/passwd file you've taken from the target machine
[path to shadow] - The file that contains the copy of the /etc/shadow file you've taken from the target machine

> john --wordlist=/usr/share/wordlists/rockyou.txt --format=sha512crypt etchashes.txt

![image](https://user-images.githubusercontent.com/44063862/159829261-05f0ccc2-2a2b-49a6-9ae1-b6ca008d6ecb.png)

### Task 7 Single Crack Mode

```
https://crackstation.net/
```

### Task 9 Cracking Password Protected Zip Files

Use **Zip2John** to convert the zip file into a hash format (John lang)

> zip2john secure.zip > zip_hash.txt

> john --wordlist=/usr/share/wordlists/rockyou.txt zip_hash.txt

![image](https://user-images.githubusercontent.com/44063862/159833276-e0a0563f-a392-4704-bcd3-d43c749072cc.png)

> unzip secure.zip 

![image](https://user-images.githubusercontent.com/44063862/159833502-4ed3b0e5-7cb9-44e5-991a-0ce0b61e7c76.png)

> cat zippy/flag.txt 

![image](https://user-images.githubusercontent.com/44063862/159833546-44104598-e237-4262-91d2-76977ebe9d58.png)

### Task 10 Cracking Password Protected RAR Archives

Use **rar2john** to convert the rar file into a hash format (John lang)

> rar2john secure.rar > rar_hash.txt

> john --wordlist=/usr/share/wordlists/rockyou.txt rar_hash.txt

![image](https://user-images.githubusercontent.com/44063862/159835172-06070867-5792-4246-8bcd-0a6579745205.png)







