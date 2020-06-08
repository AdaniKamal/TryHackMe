# Custom Wordlists

## Task 3 - Filter Wordlists

### Get flag 1 - Password Requirements: 8 length minimum

```
cat /usr/share/wordlists/rockyou.txt | grep -x '.\{8,20\}' > 8-20_length_wordlist
```

```
zip2john flag1.txt.zip > flag1hash
```

```
john flag1hash --wordlist=8-20_length_wordlist
```

![image](https://user-images.githubusercontent.com/44063862/84015557-9eb09e00-a9ae-11ea-8604-67d1ea2d7997.png)

*Use the password to unzip protected zip file. And get the flag.

### Get flag2 - Password Requirements: 1 Uppercase

```
cat /usr/share/wordlists/rockyou.txt | grep -o '[^ ]*[A-Z][^ ]*' > contains_uppercase.txt
```

```
zip2john flag2.txt.zip > flag2hash
```

```
john flag2hash --wordlist=contains_uppercase.txt
```

### Get flag 3 - Password Requirements: 10 length minimum, Uppercase, Special Characters

For this questions, it is need many steps.

* First, we will find a 10 lenght word from our Uppercase file (from Challangge 2)

```
cat contains_uppercase.txt | grep -x '.\{10,20\}' > 10-20_length_wordlist
```

* Now, step is the same, but now againts the above file.

```
cat 10-20_length_wordlist | grep -v “^[A-Za-z0-9]*$” > contains_special.txt
```

```
zip2john flag3.txt.zip > flag3hash
```

```
john flag3hash --wordlist=contains_special.txt
```

**By _AdaniKamal_**
