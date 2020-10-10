# Web Fundamentals

![image](https://user-images.githubusercontent.com/44063862/95646552-2db7f900-0afc-11eb-869f-1c0ede4524af.png)

------------------------------------------------------------------------------------------------------------------------
**HINT:**

* GET request. Make a GET request to the web server with path /ctf/get
* POST request. Make a POST request with the body "flag_please" to /ctf/post
* Get a cookie. Make a GET request to /ctf/getcookie and check the cookie the server gives you
* Set a cookie. Set a cookie with name "flagpls" and value "flagpls" in your devtools and make a GET request to /ctf/sendcookie

```
nmap -A 10.10.24.60
```

![image](https://user-images.githubusercontent.com/44063862/95646578-6788ff80-0afc-11eb-999f-f95c867a95b5.png)

Then browse http://10.10.95.82:PORT

## What's the GET flag?

http://10.10.95.82:PORT/ctf/get

![image](https://user-images.githubusercontent.com/44063862/95646692-b2efdd80-0afd-11eb-8b2b-86c84cdd16cf.png)

## What's the POST flag?

```
curl 10.10.95.82:PORT/ctf/post -X POST --data "flag_please"
```

![image](https://user-images.githubusercontent.com/44063862/95646758-3ad5e780-0afe-11eb-915d-8db3be316c6a.png)

## What's the "Get a cookie" flag?

http://10.10.95.82:PORT/ctf/getcookie

![image](https://user-images.githubusercontent.com/44063862/95646797-9607da00-0afe-11eb-9246-eacb6cbdc646.png)

## What's the "Set a cookie" flag?

http://10.10.95.82:PORT/ctf/sendcookie

Set:
* cookie with name "flagpls"
* value "flagpls" 

![image](https://user-images.githubusercontent.com/44063862/95646864-22b29800-0aff-11eb-8c2c-48389c86f6f0.png)

CONGRATULATIONS!! 

Thank you for reading. :)

**By _AdaniKamal_**
