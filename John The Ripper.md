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

