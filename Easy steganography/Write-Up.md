# Easy steganography

## 1.	Flag1.jpeg

Given flag1.jpeg. I try using Exiftool, Binwalk. But it leads me nowhere. Then I try HxD (Hexeditor). 
It is quite hard because I do not know the flag structure. I search for THM, TryHackMe, tryhackme, Steganography, then finally **St** 

![image](https://user-images.githubusercontent.com/44063862/82633208-1cde1800-9c2d-11ea-83f5-4370e6cc07da.png)

**Flag: St3g4n0**

## 2.	Flag2.jpeg

I Binwalk this image and get that there is an image inside it.

> Binwalk flag2.jpeg

![image](https://user-images.githubusercontent.com/44063862/82633226-26678000-9c2d-11ea-88b1-0fd8263e8169.png)

So, I try to extract it.

>Binwalk -e flag2.jpeg

But, it failed. Erm… 

> binwalk --dd '.*' flag2.jpeg

![image](https://user-images.githubusercontent.com/44063862/82633236-31221500-9c2d-11ea-93dc-e3b78373a15c.png)

It get extracted by flag --dd . There is a picture. Open it.

![image](https://user-images.githubusercontent.com/44063862/82633257-3d0dd700-9c2d-11ea-99dc-c31512e85f91.png)

**Flag: ALGORITHM**

## 3.	Flag3.jpeg

>Exiftool flag3.jpeg

![image](https://user-images.githubusercontent.com/44063862/82633284-50b93d80-9c2d-11ea-84cd-1d1baccc80b6.png)

There is passphrase **Math**

I try steghide, but 3rr0r. Hmmm. Try submit “Math” as flag. BINGO!

**Flag: Math**

## 4.	Flag4.jpeg

> binwalk --dd '.*' flag3.jpeg

![image](https://user-images.githubusercontent.com/44063862/82633307-5c0c6900-9c2d-11ea-9079-7a139b70ae22.png)

There is xml file. Open the XML file. Scroll down until I found **”TryHardered”**

![image](https://user-images.githubusercontent.com/44063862/82633324-66c6fe00-9c2d-11ea-94fc-e7335beed8a0.png)

**Flag: TryHardered**

**By _AdaniKamal_**
