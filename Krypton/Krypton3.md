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

The encrypted password in krypton4 is 'KSVVW BGSJD SVSIS VXBMN YQUUK BNWCU ANMJS'

The file `found1` has a encrypted block of cipher text. Both found2 and found3 have similar blocks of cipher text.

```bash
krypton3@krypton:/krypton/krypton3$ cat found1
CGZNL YJBEN QYDLQ ZQSUQ NZCYD SNQVU BFGBK GQUQZ QSUQN UZCYD SNJDS UDCXJ ZCYDS NZQSU QNUZB WSBNZ QSUQN UDCXJ CUBGS BXJDS UCTYV SUJQG WTBUJ KCWSV LFGBK GSGZN LYJCB GJSZD GCHMS UCJCU QJLYS BXUMA UJCJM JCBGZ CYDSN CGKDC ZDSQZ DVSJJ SNCGJ DSYVQ CGJSO JCUNS YVQZS WALQV SJJSN UBTSX COSWG MTASN BXYBU CJCBG UWBKG JDSQV YDQAS JXBNS OQTYV SKCJD QUDCX JBXQK BMVWA SNSYV QZSWA LWAKB MVWAS ZBTSS QGWUB BGJDS TSJDB WCUGQ TSWQX JSNRM VCMUZ QSUQN KDBMU SWCJJ BZBTT MGCZQ JSKCJ DDCUE SGSNQ VUJDS SGZNL YJCBG UJSYY SNXBN TSWAL QZQSU QNZCY DSNCU BXJSG CGZBN YBNQJ SWQUY QNJBX TBNSZ BTYVS OUZDS TSUUM ZDQUJ DSICE SGNSZ CYDSN QGWUJ CVVDQ UTBWS NGQYY VCZQJ CBGCG JDSNB JULUJ STQUK CJDQV VUCGE VSQVY DQASJ UMAUJ CJMJC BGZCY DSNUJ DSZQS UQNZC YDSNC USQUC VLANB FSGQG WCGYN QZJCZ SBXXS NUSUU SGJCQ VVLGB ZBTTM GCZQJ CBGUS ZMNCJ LUDQF SUYSQ NSYNB WMZSW TBUJB XDCUF GBKGK BNFAS JKSSG QGWDC USQNV LYVQL UKSNS TQCGV LZBTS WCSUQ GWDCU JBNCS UESGN SUDSN QCUSW JBJDS YSQFB XUBYD CUJCZ QJCBG QGWQN JCUJN LALJD SSGWB XJDSU COJSS GJDZS GJMNL GSOJD SKNBJ STQCG VLJNQ ESWCS UMGJC VQABM JCGZV MWCGE DQTVS JFCGE VSQNQ GWTQZ ASJDZ BGUCW SNSWU BTSBX JDSXC GSUJS OQTYV SUCGJ DSSGE VCUDV QGEMQ ESCGD CUVQU JYDQU SDSKN BJSJN QECZB TSWCS UQVUB FGBKG QUNBT QGZSU QGWZB VVQAB NQJSW KCJDB JDSNY VQLKN CEDJU TQGLB XDCUY VQLUK SNSYM AVCUD SWCGS WCJCB GUBXI QNLCG EHMQV CJLQG WQZZM NQZLW MNCGE DCUVC XSJCT SQGWC GJKBB XDCUX BNTSN JDSQJ NCZQV ZBVVS QEMSU YMAVC UDSWJ DSXCN UJXBV CBQZB VVSZJ SWSWC JCBGB XDCUW NQTQJ CZKBN FUJDQ JCGZV MWSWQ VVAMJ JKBBX JDSYV QLUGB KNSZB EGCUS WQUUD QFSU
```

The hints in the directory suggest using frequency analysis to solve this problem.
Using a tool online, you can analyze the most common trigrams and use frequency analysis to make your own key:

An example is that the most common trigram in the block `JDS` translates to the most common trigram in the english language `THE`. So J becomes T, D becomes H, and S becomes E. 

Cipher -   a b c d e f g h i j k l m n o p
Alphabet - b o i h g k n q v t w y u r x z
Cipher -   q r s t u v w x y z
Alphabet - a j e m s l d f p c

Using this same key, we can decrypt the password.
KSVVW BGSJD SVSIS VXBMN YQUUK BNWCU ANMJS
WELLD ONETH ELEVE LFOUR PASWW ORDIS BRUTE

`WELL DONE THE LEVEL FOUR PASSWORD IS BRUTE`
