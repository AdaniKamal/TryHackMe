# Day 14 - Unknown storage

![image](https://user-images.githubusercontent.com/44063862/83961094-7ba8c000-a8c2-11ea-8343-e1037d87a820.png)

Bucket name: advent-bucket-one

##Q1 - 	What is the name of the file you found?

```
curl advent-bucket-one.s3.amazonaws.com | xmllint --format -
```

* gets a copy of the page which is comprised of an XML document
* xmllint will give us a pretty printed version of the file

![image](https://user-images.githubusercontent.com/44063862/83961122-c0345b80-a8c2-11ea-98b3-5d777e64f82c.png)

##Q2 - 	What is in the file?

```
curl advent-bucket-one.s3.amazonaws.com/employee_names.txt
```

**By _AdaniKamal_**
