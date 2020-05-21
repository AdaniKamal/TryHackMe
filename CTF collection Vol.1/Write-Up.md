# CTF collection Vol.1

## 1. What does the base said?

![image](https://user-images.githubusercontent.com/44063862/82412111-9c40df80-9aa5-11ea-9caa-ab82757c9a1f.png)

BY the given encoded, we know that this is **BASE 64** VEhNe2p1NTdfZDNjMGQzXzdoM19iNDUzfQ==

So, heat up our "oven" [CyberChef](https://gchq.github.io/CyberChef/)

![image](https://user-images.githubusercontent.com/44063862/82412119-9f3bd000-9aa5-11ea-9878-0922af9b6776.png)

**Flag: THM{ju57_d3c0d3_7h3_b453}**

## 2.	Meta Meta

![image](https://user-images.githubusercontent.com/44063862/82412186-c85c6080-9aa5-11ea-84a0-214378df02e0.png)

This is the given picture. (Find Me.jpg)

![Findme](https://user-images.githubusercontent.com/44063862/82414061-0ad36c80-9aa9-11ea-836f-156f10b58d3d.jpg)

Hint is in the title itself. Meta = Metadata. Usually I will use exiftool in linux. 
But, today i want to share new online tools for exiftool.

[metapicz](http://metapicz.com/#landing)

![image](https://user-images.githubusercontent.com/44063862/82414075-13c43e00-9aa9-11ea-9bff-1f1f1a6a7391.png)

**Flag: THM{3x1f_0r_3x17}**

## 3. Mon, are we going to be okay

![image](https://user-images.githubusercontent.com/44063862/82414329-7289b780-9aa9-11ea-8c0c-b9064f4d47f6.png)

This is the picture that they give.

![Extinction](https://user-images.githubusercontent.com/44063862/82418208-496c2580-9aaf-11ea-984e-af1bbc042558.jpg)

Well, just try online stega tools.

[Steganographic Decoder](https://futureboy.us/stegano/decinput.html)

![image](https://user-images.githubusercontent.com/44063862/82414339-787f9880-9aa9-11ea-97f3-296e63aff8a0.png)

**Flag: THM{500n3r_0r_l473r_17_15_0ur_7urn}**

## 4.	Erm......Magick

![image](https://user-images.githubusercontent.com/44063862/82414452-a95fcd80-9aa9-11ea-8ab9-76aa0a42913d.png)

This was like free flag. i didn't mean to get this one. Lucky I found it.

![image](https://user-images.githubusercontent.com/44063862/82414458-abc22780-9aa9-11ea-92aa-bce4ae5447c8.png)

**Flag: THM{wh173_fl46}**

## 5.	QRrrrr

![image](https://user-images.githubusercontent.com/44063862/82414539-c6949c00-9aa9-11ea-8a70-177e3d867973.png)

They give QR Code. So, just find QR Code Decode

[ZXing Decoder Online](https://zxing.org/w/decode.jspx)

![image](https://user-images.githubusercontent.com/44063862/82414549-c8f6f600-9aa9-11ea-991b-c7085cea7fa3.png)

**Flag: THM{qr_m4k3_l1f3_345y}**

## 6.	Reverse it or read it?

![image](https://user-images.githubusercontent.com/44063862/82414623-ecba3c00-9aa9-11ea-8e63-76acef077728.png)

I try to run this file. 

```
./hello.hello
```

![image](https://user-images.githubusercontent.com/44063862/82414628-ef1c9600-9aa9-11ea-920d-8631b2f7605b.png)

But I didn't get anything. Just a simple hello. So. I try to read this file by run this command

```
strings hello.hello
```

![image](https://user-images.githubusercontent.com/44063862/82414632-f17ef000-9aa9-11ea-89b8-f109e176ad3d.png)

**Flag: THM{345y_f1nd_345y_60}**

## 7.	Another decoding stuff

![image](https://user-images.githubusercontent.com/44063862/82416559-cfd33800-9aac-11ea-9429-85ae3973486b.png)

I try **Magic** in CyberChef 3agrSy1CewF9v8ukcSkPSYm3oKUoByUpKG4L

It's Base 58.

[CyberChef](https://gchq.github.io/CyberChef/)

![image](https://user-images.githubusercontent.com/44063862/82417203-c7c7c800-9aad-11ea-9292-a8f12e3198f9.png)

**Flag: THM{17_h45_l3553r_l3773r5}**

## 8.	Left or right

![image](https://user-images.githubusercontent.com/44063862/82416658-fa24f580-9aac-11ea-8e56-a7617b902669.png)

MAF{atbe_max_vtxltk}

"Rot 13 is too mainstream" but we sure that this is Rot something. So, using cyberchef, rot until found the flag. 
It is Rot 33.

[CyberChef](https://gchq.github.io/CyberChef/)

![image](https://user-images.githubusercontent.com/44063862/82416665-fd1fe600-9aac-11ea-85f7-92523308ea81.png)

**Flag: THM{hail_the_caesar}**

## 9.	Make a comment

![image](https://user-images.githubusercontent.com/44063862/82416718-1aed4b00-9aad-11ea-8b06-6d5a25ac9adf.png)

We have no source for this challenge. Why don't we check "Inspect".

![image](https://user-images.githubusercontent.com/44063862/82416721-1cb70e80-9aad-11ea-8457-7e9d41dcd2ec.png)

**Flag: THM{4lw4y5_ch3ck_7h3_c0m3mn7}**

## 10.	Can you fix it?

![image](https://user-images.githubusercontent.com/44063862/82416803-3fe1be00-9aad-11ea-9b3a-0e5459e20f20.png)

He said he messed up with this PNG file. So, we open up HxD/hexeditor to check the header/footer of this file.

![image](https://user-images.githubusercontent.com/44063862/82416809-42dcae80-9aad-11ea-8410-95f99f3ea083.png)

Yaa, he messed it up. As we can see, wrong header.

Search [List of signatures](https://en.wikipedia.org/wiki/List_of_file_signatures)

This is a signature header for PNG file.

![image](https://user-images.githubusercontent.com/44063862/82416824-45d79f00-9aad-11ea-8243-deeaca08d3d0.png)

Change and save it.

![image](https://user-images.githubusercontent.com/44063862/82416829-47a16280-9aad-11ea-9396-33e0eaf9fdb0.png)

![repair](https://user-images.githubusercontent.com/44063862/82419985-b7195100-9ab1-11ea-96ab-0523b58b1261.png)

**Flag: THM{y35_w3_c4n}**

## 11.	Read it

![image](https://user-images.githubusercontent.com/44063862/82420288-1d9e6f00-9ab2-11ea-9441-ad124761daa2.png)

Find all possible tryhackme account until it lead too tryhackme reddit account where the flag is.

[tryhackme - reddit](https://www.reddit.com/r/tryhackme/)

![image](https://user-images.githubusercontent.com/44063862/82420309-22fbb980-9ab2-11ea-8d83-1852b9d31e41.png)

**Flag: THM{50c14l_4cc0un7_15_p4r7_0f_051n7}**

## 12.	Spin my head

![image](https://user-images.githubusercontent.com/44063862/82420592-80900600-9ab2-11ea-95b2-8ef28c4ecb95.png)

> ++++++++++[>+>+++>+++++++>++++++++++<<<<-]>>>++++++++++++++.------------.+++++.>+++++++++++++++++++++++.<<++++++++++++++++++.>>-------------------.---------.++++++++++++++.++++++++++++.<++++++++++++++++++.+++++++++.<+++.+.>----.>++++.

This is [Brain Fuck](https://en.wikipedia.org/wiki/Brainfuck)

Find Online tools.

[Brainfuck](https://www.dcode.fr/brainfuck-language)

![image](https://user-images.githubusercontent.com/44063862/82420782-c77dfb80-9ab2-11ea-8824-2f7a73b18c7e.png)

**Flag: THM{0h_my_h34d}**

## 13.	An exclusive!

![image](https://user-images.githubusercontent.com/44063862/82421047-1166e180-9ab3-11ea-818d-abb51d573ed6.png)

> S1: 44585d6b2368737c65252166234f20626d
S2: 1010101010101010101010101010101010

By using [CyberChef](https://gchq.github.io/CyberChef/), we try Hex then XOR.

![image](https://user-images.githubusercontent.com/44063862/82421088-1fb4fd80-9ab3-11ea-9f69-57f8e8114e48.png)

**Flag: THM{3xclu51v3_0r}**

## 14.	Binary Walk

![image](https://user-images.githubusercontent.com/44063862/82421157-378c8180-9ab3-11ea-858f-e128cd95b9bd.png)

So, fire up our kali to **Binwalk** this file

![image](https://user-images.githubusercontent.com/44063862/82421168-39eedb80-9ab3-11ea-9d50-1b3d1ce5126a.png)

```
binwalk -e hell.jpg
```

![image](https://user-images.githubusercontent.com/44063862/82421180-3ce9cc00-9ab3-11ea-9e1f-d4b4c4383d81.png)

**Flag: THM{y0u_w4lk_m3_0u7}**

## 15.	Darkness

![image](https://user-images.githubusercontent.com/44063862/82421596-cef1d480-9ab3-11ea-88a9-29100a356f79.png)

"Lurking in the dark" it sounds like a hint. I try using **Stegsolve**

![image](https://user-images.githubusercontent.com/44063862/82421603-d1ecc500-9ab3-11ea-8a4b-911b5d073e19.png)

**Flag: THM{7h3r3_15_h0p3_1n_7h3_d4rkn355}**

## 16.	A sounding QR

![image](https://user-images.githubusercontent.com/44063862/82421784-255f1300-9ab4-11ea-8da6-7488edb83ba8.png)

Well, just try QR Decode online tools. [ZXing Decoder Online](https://zxing.org/w/decode.jspx)

![image](https://user-images.githubusercontent.com/44063862/82421789-28f29a00-9ab4-11ea-925c-33e5f770a6a1.png)

We get link after decode. https://soundcloud.com/user-86667759/thm-ctf-vol1

![image](https://user-images.githubusercontent.com/44063862/82421802-2c862100-9ab4-11ea-85d4-e4a5cbe50f69.png)

**Flag: THM{SOUNDINGQR}**

## 17.	Dig up the past

![image](https://user-images.githubusercontent.com/44063862/82421998-7838ca80-9ab4-11ea-849c-dfa2e7a4636c.png)

I go to the link. https://www.embeddedhacker.com/

But, unfortunately! We don’t get anything for the given date. https://www.embeddedhacker.com/2020/01/hacking-walkthrough-ctflearn-crypto-medium/

Well, I need hint.

![image](https://user-images.githubusercontent.com/44063862/82422151-aa4a2c80-9ab4-11ea-89e8-b61e024efa37.png)

Erm, Wayback Machine. Okay, Mr Google. I need your help. 

[Wayback Machine](https://archive.org/web/)

Put in our link that was given from the challenge.

![image](https://user-images.githubusercontent.com/44063862/82422164-ad451d00-9ab4-11ea-84d5-a8a67a4ebd09.png)

Find January 2, 2020 from the calendar.

![image](https://user-images.githubusercontent.com/44063862/82422170-afa77700-9ab4-11ea-9989-f6cec395cd83.png)

Click on [13:12:52](https://web.archive.org/web/20200102131252/https://www.embeddedhacker.com/). Scroll until found our flag.

![image](https://user-images.githubusercontent.com/44063862/82422176-b2a26780-9ab4-11ea-9a14-dd60f06b1d69.png)

**Flag: THM{ch3ck_th3_h4ckb4ck}**

## 18.	Uncrackable!

![image](https://user-images.githubusercontent.com/44063862/82422603-3bb99e80-9ab5-11ea-9875-c2173f9397c7.png)

MYKAHODTQ{RVG_YVGGK_FAL_WXF} . Well, seems like vigenere without a key to me.

[Vigenere Solver](https://www.guballa.de/vigenere-solver)

![image](https://user-images.githubusercontent.com/44063862/82422610-3e1bf880-9ab5-11ea-96b5-385199a5df12.png)

**Flag: TRYHACKME{YOU_FOUND_THE_KEY}**

## 19.	Small Bases

![image](https://user-images.githubusercontent.com/44063862/82422857-9521cd80-9ab5-11ea-9278-3d56ce34f5c0.png)

> 581695969015253365094191591547859387620042736036246486373595515576333693

First, I decode [Decimal-Hex](https://www.rapidtables.com/convert/number/decimal-to-hex.html)

![image](https://user-images.githubusercontent.com/44063862/82422864-981cbe00-9ab5-11ea-9167-5686084103ab.png)

Then, [Hex-Ascii](https://www.rapidtables.com/convert/number/hex-to-ascii.html)

![image](https://user-images.githubusercontent.com/44063862/82422873-9a7f1800-9ab5-11ea-8f12-583a90c9ebf9.png)

**Flag: THM{17_ju57_4n_0rd1n4ry_b4535}**

## 20.	Read the packet

![image](https://user-images.githubusercontent.com/44063862/82423262-2133f500-9ab6-11ea-9325-d6df5eeb7d6e.png)

Open up pcap file using Wireshark

Then, File - Export object - HTTP

![image](https://user-images.githubusercontent.com/44063862/82423275-24c77c00-9ab6-11ea-9e51-dd3175ae775e.png)

Click on flag.txt – Save

![image](https://user-images.githubusercontent.com/44063862/82423286-26913f80-9ab6-11ea-9abb-64b61405fb7f.png)

**Flag: THM{d0_n07_574lk_m3}**

DONE!!

Thank you for reading my writeup.

**By _©AdaniKamal_**
