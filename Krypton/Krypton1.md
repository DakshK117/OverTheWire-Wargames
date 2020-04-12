# OverTheWire Project

### [Project Krypton:](http://overthewire.org/wargames/krypton/)

#### Krypton Level 0 -> 1 and 1-> 2

The first level gives us the password which is encrypted.

>he following string encodes the password using Base64: S1JZUFRPTklTR1JFQVQ=

Doing `man base64` shows us that the option `--decode` will decode the inputed file if it is encoded.

Running `base64 --decode` on a file with the encoded string will return `KRYPTONISGREAT`

Use this password to ssh into the first level:

`$ssh krypton1@krypton.labs.overthewire.org -p2222`

The directory has two files:

```bash
krypton1@krypton:/krypton/krypton1$ ls -l -a
total 16
drwxr-xr-x 2 root     root     4096 Dec 31 05:17 .
drwxr-xr-x 8 root     root     4096 Dec 31 05:18 ..
-rw-r----- 1 krypton1 krypton1  882 Dec 31 05:17 README
-rw-r----- 1 krypton1 krypton1   26 Dec 31 05:17 krypton2
krypton1@krypton:/krypton/krypton1$
```

The website tells us
>The password for level 2 is in the file ‘krypton2’. It is ‘encrypted’ using a simple rotation. It is also in non-standard ciphertext format. When using alpha characters for cipher text it is normal to group the letters into 5 letter clusters, regardless of word boundaries. This helps obfuscate any patterns. This file has kept the plain text word boundaries and carried them to the cipher text. Enjoy

```bash
krypton1@krypton:/krypton/krypton1$ cat krypton2  
YRIRY GJB CNFFJBEQ EBGGRA
```

So we know the password which is encoded in rot13 is `YRIRY GJB CNFFJBEQ EBGGRA`

To decrypt rot13 we can use the command `tr` which "translates or deletes characters"

```bash
krypton1@krypton:/krypton/krypton1$ echo 'YRIRY GJB CNFFJBEQ EBGGRA' | tr '[A-Za-z]' '[N-ZA-Mn-za-m]'
LEVEL TWO PASSWORD ROTTEN
```

So the password for krypton2 is `ROTTEN`
