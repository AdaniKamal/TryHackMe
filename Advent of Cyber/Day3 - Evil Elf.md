# Day3 - Evil Elf

## Q1 - Go straight to no. 998 and take the dest IP.

## Q2 

* Filter: Telnet ( to identify where someone was using telnet to execute commands on a remote machine!)

![image](https://user-images.githubusercontent.com/44063862/83956591-5e5bfd80-a892-11ea-905e-aa9bcdbe3759.png)

## Q3 -

Crack password Buddy. Follow TCP stream.

![image](https://user-images.githubusercontent.com/44063862/83956631-bd217700-a892-11ea-857d-13b99d4038a1.png)

```
hashcat --force -m 1800 /root/Desktop/buddy.txt /root/List/rockyou.txt --session sha512
```

Output:

```
root@kali:~# hashcat --force -m 1800 /root/Desktop/buddy.txt /root/List/rockyou.txt --session sha512hashcat (v5.1.0) starting...

OpenCL Platform #1: The pocl project
====================================
* Device #1: pthread-Intel(R) Core(TM) i5-9300H CPU @ 2.40GHz, 512/1488 MB allocatable, 4MCU

Hashes: 1 digests; 1 unique digests, 1 unique salts
Bitmaps: 16 bits, 65536 entries, 0x0000ffff mask, 262144 bytes, 5/13 rotates
Rules: 1

Applicable optimizers:
* Zero-Byte
* Single-Hash
* Single-Salt
* Uses-64-Bit

Minimum password length supported by kernel: 0
Maximum password length supported by kernel: 256

ATTENTION! Pure (unoptimized) OpenCL kernels selected.
This enables cracking passwords and salts > length 32 but for the price of drastically reduced performance.
If you want to switch to optimized OpenCL kernels, append -O to your commandline.

Watchdog: Hardware monitoring interface not found on your system.
Watchdog: Temperature abort trigger disabled.

* Device #1: build_opts '-cl-std=CL1.2 -I OpenCL -I /usr/share/hashcat/OpenCL -D LOCAL_MEM_TYPE=2 -D VENDOR_ID=64 -D CUDA_ARCH=0 -D AMD_ROCM=0 -D VECT_SIZE=4 -D DEVICE_TYPE=2 -D DGST_R0=0 -D DGST_R1=1 -D DGST_R2=2 -D DGST_R3=3 -D DGST_ELEM=16 -D KERN_TYPE=1800 -D _unroll'                                      
Dictionary cache hit:
* Filename..: /root/List/rockyou.txt
* Passwords.: 14344385
* Bytes.....: 139921504
* Keyspace..: 14344385

$6$3GvJsNPG$ZrSFprHS13divBhlaKg1rYrYLJ7m1xsYRKxlLh0A1sUc/6SUd7UvekBOtSnSyBwk3vCDqBhrgxQpkdsNN6aYP1:rainbow
                                                 
Session..........: sha512
Status...........: Cracked
Hash.Type........: sha512crypt $6$, SHA512 (Unix)
Hash.Target......: $6$3GvJsNPG$ZrSFprHS13divBhlaKg1rYrYLJ7m1xsYRKxlLh0...N6aYP1
Time.Started.....: Sat Jun  6 19:35:17 2020 (3 secs)
Time.Estimated...: Sat Jun  6 19:35:20 2020 (0 secs)
Guess.Base.......: File (/root/List/rockyou.txt)
Guess.Queue......: 1/1 (100.00%)
Speed.#1.........:       82 H/s (10.05ms) @ Accel:64 Loops:32 Thr:1 Vec:4
Recovered........: 1/1 (100.00%) Digests, 1/1 (100.00%) Salts
Progress.........: 256/14344385 (0.00%)
Rejected.........: 0/256 (0.00%)
Restore.Point....: 0/14344385 (0.00%)
Restore.Sub.#1...: Salt:0 Amplifier:0-1 Iteration:4992-5000
Candidates.#1....: secret -> samsung

Started: Sat Jun  6 19:35:06 2020
Stopped: Sat Jun  6 19:35:22 2020
```

