# Crack The Hash

## LEVEL 1

### 1. 48bb6e862e54f2a795ffc4e541caed4d

I use Hash Anylyzer to analyse the given Hash. [Hash Analyzer](https://www.tunnelsup.com/hash-analyzer/)

![image](https://user-images.githubusercontent.com/44063862/82433858-a1f9ed80-9ac4-11ea-8613-6f49f934700e.png)

So, based on the output it is [MD5 Decryption]( https://www.md5online.org/md5-decrypt.html)

![image](https://user-images.githubusercontent.com/44063862/82433869-a4f4de00-9ac4-11ea-84c5-e16c1e38c806.png)

**Answer: easy**

### 2. CBFDAC6008F9CAB4083784CBD1874F76618D2A97 

I think for the rest of question also i will using this tool. [Hash Analyzer](https://www.tunnelsup.com/hash-analyzer/)

![image](https://user-images.githubusercontent.com/44063862/82434261-32d0c900-9ac5-11ea-8157-e87aa9a78c98.png)

So, based on the output it is SHA1 [Hashes]( https://hashes.com/en/decrypt/hash)

![image](https://user-images.githubusercontent.com/44063862/82434269-349a8c80-9ac5-11ea-81fc-e99d46678d54.png)

I check 70617373776f7264313233 in [Hash Analyzer](https://www.tunnelsup.com/hash-analyzer/). It say to be Hex.

So, I hex(decode) this 70617373776f7264313233 using [CyberChef]( https://www.tunnelsup.com/hash-analyzer/)

![image](https://user-images.githubusercontent.com/44063862/82434628-b7bbe280-9ac5-11ea-89a6-8ee67b9369a8.png)

**Answer: password123**

### 3. 1C8BFE8F801D79745C4631D09FFF36C82AA37FC4CCE4FC946683D7B336B63032 

[Hash Analyzer](https://www.tunnelsup.com/hash-analyzer/)

![image](https://user-images.githubusercontent.com/44063862/82434799-fb165100-9ac5-11ea-820b-8dc46c2be78f.png)

It is SHA256 [Hashes]( https://hashes.com/en/decrypt/hash)

![image](https://user-images.githubusercontent.com/44063862/82434809-fce01480-9ac5-11ea-916e-0a3255d19977.png)

**Answer: letmein**

### 4. $2y$12$Dwt1BZj6pcyc3Dy1FWZ5ieeUznr71EeNkJkUlypTsgbX1H68wsRom 

[Hash Analyzer](https://www.tunnelsup.com/hash-analyzer/)

![image](https://user-images.githubusercontent.com/44063862/82434988-3ca6fc00-9ac6-11ea-8ead-2774dd391967.png)

It is bcrypt. I google the hash.

![image](https://user-images.githubusercontent.com/44063862/82435147-724be500-9ac6-11ea-991e-995803e53ca9.png)

[Identifying and Cracking Hashes](https://medium.com/infosec-adventures/identifying-and-cracking-hashes-7d580b9fd7f1)

CTRL + F

![image](https://user-images.githubusercontent.com/44063862/82435154-74ae3f00-9ac6-11ea-9f7a-124d2960f896.png)

**Answer: bleh**

### 5. 279412f945939ba78ce0758d3fd83daa

[Hash Analyzer](https://www.tunnelsup.com/hash-analyzer/)

![image](https://user-images.githubusercontent.com/44063862/82435357-c3f46f80-9ac6-11ea-9662-d91976eafc1f.png)

Output is MD5. [Hashes]( https://hashes.com/en/decrypt/hash)

![image](https://user-images.githubusercontent.com/44063862/82435473-ef775a00-9ac6-11ea-9706-02741bf0c681.png)

**Answer: bleh**

**_By AdaniKamal_**














