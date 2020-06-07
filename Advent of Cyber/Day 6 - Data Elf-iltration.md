# [Day 6] Data Elf-iltration

## Q1 - What data was exfiltrated via DNS?

* Open pcap using wireshark
* Search DNS

![image](https://user-images.githubusercontent.com/44063862/83958382-9b7cbb80-a8a3-11ea-9076-4682d4f873a6.png)

--> 43616e64792043616e652053657269616c204e756d6265722038343931

* Hex --> Ascii

```
echo 43616e64792043616e652053657269616c204e756d6265722038343931 | xxd -r -p
```

![image](https://user-images.githubusercontent.com/44063862/83958414-fa423500-a8a3-11ea-9752-63df514a3432.png)

## Q2 - What did Little Timmy want to be for Christmas?

* We were given a zip file.
* Password protected
* Using kali to brute force password

```
fcrackzip -b --method 2 -D -p /root/List/rockyou.txt -v ./christmaslists.zip
```

![image](https://user-images.githubusercontent.com/44063862/83958451-6e7cd880-a8a4-11ea-9e51-05a3ecf658be.png)

* Unzip the file with the password that we get.

```
unzip christmaslists.zip
```

* Find Timmy Letter. There's your answer.

## Q3 - 	What was hidden within the file?

* With the picture that we get. Try all steganography tools.

1) strings
2) exiftool
3) binwalk
4) steghide

* Steghide

```
steghide --extract -sf TryHackMe.jpg
```

![image](https://user-images.githubusercontent.com/44063862/83958516-5a85a680-a8a5-11ea-833a-d8fe1feb2c01.png)

* Just enter through the password.
* It will extract a file for us. 

**By _AdaniKamal_**
