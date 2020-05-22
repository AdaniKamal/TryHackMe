# stealthcopter ctf primer1

## Flag 1

![image](https://user-images.githubusercontent.com/44063862/82668145-baf0d300-9c6b-11ea-939f-935a0e89360b.png)

Check Source Code

![image](https://user-images.githubusercontent.com/44063862/82668153-bdebc380-9c6b-11ea-9d99-abc99f58832d.png)

**FLAG{check_the_comments_lol}**

## Flag 2

Just as before, I opened the source code. I see js file there.

![image](https://user-images.githubusercontent.com/44063862/82668184-d0fe9380-9c6b-11ea-8120-0679e7720fbe.png)

## Flag 3
View source code.

And I see code "Base64" Copy to the Cyber Chef.

![image](https://user-images.githubusercontent.com/44063862/82668245-effd2580-9c6b-11ea-8206-912a970448eb.png)

**FLAG{h4ck_t1m3}**

## Flag 4

Open the given php w.o4.php

![image](https://user-images.githubusercontent.com/44063862/82668276-fe4b4180-9c6b-11ea-9b98-d1ca906b967e.png)

I try run using online tools. http://www.writephponline.com/

But it did not display anything.

I try to delete // (Comment). Ta-Da!

![image](https://user-images.githubusercontent.com/44063862/82668296-086d4000-9c6c-11ea-86e5-f397dbc0ec9e.png)

**FLAG{php_is_a_b4d_l4ngu4g3}**

## Flag 5
Run the script in kali and do the test.

![image](https://user-images.githubusercontent.com/44063862/82668324-158a2f00-9c6c-11ea-829d-a88b4b92193e.png)

So, it is a brute force. So, I entered one by one number 1-9. 

BINGO!

```
php w.05.php ‘key=7’
```

![image](https://user-images.githubusercontent.com/44063862/82668341-1f139700-9c6c-11ea-996a-44a9f7c046e9.png)

**FLAG{n0t_s0_t0ugh}**

## FLAG 6

## FLAG 7

## FLAG 8

Open the JWT

> eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MTIzNCwidXNlcm5hbWUiOiJhZG1pbiIsInBhc3N3b3JkIjoiRkxBR3tqd3RfdDBrM25zX2FyM19jMDBsX2IzNG56fSJ9.gNVX4fCIMvjLYZ0jUY0untMYbPmRNNFzZwXyU01bv-M

Search for JWT, and fount this website.

https://www.jsonwebtoken.io/

![image](https://user-images.githubusercontent.com/44063862/82668404-41a5b000-9c6c-11ea-9cd1-e9839d334047.png)

**FLAG{jwt_t0k3ns_ar3_c00l_b34nz}**

## FLAG 9
> eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MTMzNywidXNlcm5hbWUiOiJhZG1pbiIsImhpbnQiOiJ0aGUgZmxhZyBpcyBGTEFHe3h4eHh4eHhfZDFjdDEwbjRyeV80dHQ0Y2t9IHdoZXJlIHh4eHh4eHggaXMgdGhlIHBhc3N3b3JkIHVzZWQgdG8gc2lnbiB0aGlzIHRva2VuIn0.dWwXygXbxXud7WVBBVNwBZwUXjsxUhwMmN8rFnRyVgE

Use same tools as before.

https://www.jsonwebtoken.io/

![image](https://user-images.githubusercontent.com/44063862/82668445-57b37080-9c6c-11ea-84ec-b06ebe452145.png)

FLAG{xxxxxxx_d1ct10n4ry_4tt4ck}

Hint: Password to sign this hash. So, we try Hashcat.
```
hashcat --force -m 16500 jwt.txt rockyou.txt
```

OUTPUT: 

```
hashcat (v5.1.0) starting...

OpenCL Platform #1: The pocl project
====================================
* Device #1: pthread-Intel(R) Core(TM) i5-9300H CPU @ 2.40GHz, 512/1488 MB allocatable, 4MCU

Hashes: 1 digests; 1 unique digests, 1 unique salts
Bitmaps: 16 bits, 65536 entries, 0x0000ffff mask, 262144 bytes, 5/13 rotates
Rules: 1

Applicable optimizers:
* Zero-Byte
* Not-Iterated
* Single-Hash
* Single-Salt

Minimum password length supported by kernel: 0
Maximum password length supported by kernel: 256

Watchdog: Hardware monitoring interface not found on your system.
Watchdog: Temperature abort trigger disabled.

* Device #1: build_opts '-cl-std=CL1.2 -I OpenCL -I /usr/share/hashcat/OpenCL -D LOCAL_MEM_TYPE=2 -D VENDOR_ID=64 -D CUDA_ARCH=0 -D AMD_ROCM=0 -D VECT_SIZE=8 -D DEVICE_TYPE=2 -D DGST_R0=0 -D DGST_R1=1 -D DGST_R2=2 -D DGST_R3=3 -D DGST_ELEM=16 -D KERN_TYPE=16511 -D _unroll'                           
* Device #1: Kernel m16511_a0-pure.cab82444.kernel not found in cache! Building may take a while...                                                   
Dictionary cache hit:
* Filename..: rockyou.txt
* Passwords.: 14344384
* Bytes.....: 139921497
* Keyspace..: 14344384

eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MTMzNywidXNlcm5hbWUiOiJhZG1pbiIsImhpbnQiOiJ0aGUgZmxhZyBpcyBGTEFHe3h4eHh4eHhfZDFjdDEwbjRyeV80dHQ0Y2t9IHdoZXJlIHh4eHh4eHggaXMgdGhlIHBhc3N3b3JkIHVzZWQgdG8gc2lnbiB0aGlzIHRva2VuIn0.dWwXygXbxXud7WVBBVNwBZwUXjsxUhwMmN8rFnRyVgE:rockyou
                                                 
Session..........: hashcat
Status...........: Cracked
Hash.Type........: JWT (JSON Web Token)
Hash.Target......: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MTMzNy...nRyVgE
Time.Started.....: Fri May 22 07:13:59 2020 (2 secs)
Time.Estimated...: Fri May 22 07:14:01 2020 (0 secs)
Guess.Base.......: File (rockyou.txt)
Guess.Queue......: 1/1 (100.00%)
Speed.#1.........:    31790 H/s (8.75ms) @ Accel:1024 Loops:1 Thr:1 Vec:8
Recovered........: 1/1 (100.00%) Digests, 1/1 (100.00%) Salts
Progress.........: 4096/14344384 (0.03%)
Rejected.........: 0/4096 (0.00%)
Restore.Point....: 0/14344384 (0.00%)
Restore.Sub.#1...: Salt:0 Amplifier:0-1 Iteration:0-1
Candidates.#1....: 123456 -> oooooo

Started: Fri May 22 07:13:48 2020
Stopped: Fri May 22 07:14:02 2020
```
![image](https://user-images.githubusercontent.com/44063862/82668450-5a15ca80-9c6c-11ea-9473-0e7c6bf28e1d.png)

Rockyou

**FLAG{rockyou_d1ct10n4ry_4tt4ck}**

## FLAG 10
__________________________________________________________________________________________________________

**By _AdaniKamal_**
