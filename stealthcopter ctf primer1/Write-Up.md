```
hashcat -m 16500 jwt.txt rockyou.txt 

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

