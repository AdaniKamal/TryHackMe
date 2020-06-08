# Custom Wordlists

## Task 4 - Modify Wordlists

### Get flag 4 - Password Requirements: 8 length minimum

```
cat /usr/share/wordlists/rockyou.txt | grep -x '.\{8,20\}' > 8-20_length_wordlist
```

### Get flag 5 - Password Requirements: 1 Uppercase

```
cat /usr/share/wordlists/rockyou.txt | grep -o '[^ ]*[A-Z][^ ]*' > contains_uppercase.txt
```

**By _AdaniKamal_**
