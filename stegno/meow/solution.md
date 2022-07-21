# Meow

**Challenge Type: Steganography**  


## Challenge


## Solution

1. Unzip the downloaded zip file
```bash
$ unzip challenge.zip

```

2. You will find two files
```bash
$ ls 
new.png original.png
```

3. Use command zteg to retrieve flag </br>
-a is to output everything </br>
More information can be found here.</br>
https://www.youtube.com/watch?v=OPRGfJJ8bmU&list=PL1H1sBF1VAKUOp_TVZiOTGt4nB74So8sv&index=10&t=382s
```bash
$ sudo apt install zsteg

$ zsteg -a new.png | grep -oE "FLAG{.*?}" --color=none

[?] 24 bytes of extra data after image end (IEND), offset = 0x7af6b
FLAG{I_am_not_the_flag}
FLAG{58b7eb5ebaa12a0515c0dac315aa2611}

```
## Note
zteg can only be used for png or bmp files
