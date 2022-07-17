# Meow

**Challenge Type: Steganography**  


## Challenge
You found an interesting Russian Doll from the factory...

## Solution

1. Extract flag file from image
```bash
$ unzip challenge.zip

```

2. You will find two files
```bash
ls 
new.png original.png
```

3. Use command zteg to retrieve flag
```bash
sudo apt install zsteg

zsteg -a new.png | grep -oE "FLAG{.*?}" --color=none

[?] 24 bytes of extra data after image end (IEND), offset = 0x7af6b
FLAG{I_am_not_the_flag}
FLAG{58b7eb5ebaa12a0515c0dac315aa2611}

```

