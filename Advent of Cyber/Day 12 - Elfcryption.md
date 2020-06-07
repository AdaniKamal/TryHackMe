# Day 12 - Elfcryption

## Q1 - What is the md5 hashsum of the encrypted note1 file?

```
md5sum note1.txt.gpg 
```

## Q2 - Where was elf Bob told to meet Alice?

Hint for this challange: gpg key is 25daysofchristmas

```
gpg -d note1.txt.gpg
```

![image](https://user-images.githubusercontent.com/44063862/83960463-b22f0c80-a8bb-11ea-99bd-cb7d124fb7d5.png)

## Q3 - Decrypt note2 and obtain the flag!

Hint for this challange: private password is hello

```
gpg -d note1.txt.gpg
```

![image](https://user-images.githubusercontent.com/44063862/83960929-e9ec8300-a8c0-11ea-980b-50d9a4e91de0.png)

There's our flag.

**By _AdaniKamal_**
