# OverTheWire Project

### [Project Krypton:](http://overthewire.org/wargames/krypton/)

#### Krypton Level 3 -> 4

Level Info:
>Well done. You’ve moved past an easy substitution cipher.

>The main weakness of a simple substitution cipher is repeated use of a simple key. In the previous exercise you were able to introduce arbitrary plaintext to expose the key. In this example, the cipher mechanism is not available to you, the attacker.

>However, you have been lucky. You have intercepted more than one message. The password to the next level is found in the file ‘krypton4’. You have also found 3 other files. (found1, found2, found3)

>You know the following important details:
The message plaintexts are in English (*** very important) - They were produced from the same key (*** even better!)
Enjoy.

Use the password `CAESARISEASY` to login to Krypton3
We are given four files:
```console
krypton3@krypton:/krypton/krypton3$ ls -la
total 36
drwxr-xr-x 2 root     root     4096 Dec 31 05:17 .
drwxr-xr-x 8 root     root     4096 Dec 31 05:18 ..
-rw-r----- 1 krypton3 krypton3   56 Dec 31 05:17 HINT1
-rw-r----- 1 krypton3 krypton3   37 Dec 31 05:17 HINT2
-rw-r----- 1 krypton3 krypton3  785 Dec 31 05:17 README
-rw-r----- 1 krypton3 krypton3 1542 Dec 31 05:17 found1
-rw-r----- 1 krypton3 krypton3 2128 Dec 31 05:17 found2
-rw-r----- 1 krypton3 krypton3  560 Dec 31 05:17 found3
-rw-r----- 1 krypton3 krypton3   42 Dec 31 05:17 krypton4
```
