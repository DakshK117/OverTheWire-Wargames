# OverTheWire Project

### [Project Leviathan:](http://overthewire.org/wargames/leviathan/)

#### Leviathan Level 3 -> 4
> There is no information for this level, intentionally.

After a long hiatus, I'll plan to finish these write-ups.
We left on Level 3.

SSH into the fourth level using the password `vuH0coox6m`

Running `ls -l -a` shows a directory named `.trash`
Hm, we should probably check that out.

```bash
leviathan4@leviathan:~$ ls -l -a
total 24
drwxr-xr-x  3 root root       4096 Oct 29 21:17 .
drwxr-xr-x 10 root root       4096 Oct 29 21:17 ..
-rw-r--r--  1 root root        220 May 15  2017 .bash_logout
-rw-r--r--  1 root root       3526 May 15  2017 .bashrc
-rw-r--r--  1 root root        675 May 15  2017 .profile
dr-xr-x---  2 root leviathan4 4096 Oct 29 21:17 .trash
leviathan4@leviathan:~$ cd .trash
leviathan4@leviathan:~/.trash$ ls
bin
```
Cool, so there's a file called "bin". We can use `file bin` to see what kind of file it is.

```bash
leviathan4@leviathan:~/.trash$ file bin
bin: setuid ELF 32-bit LSB executable, Intel 80386, version 1 (SYSV), dynamically linked, interpreter /lib/ld-linux.so.2, for GNU/Linux 2.6.32, BuildID[sha1]=00ce1aa55b0e691470f61baff0ee59a6c33fcb50, not stripped
```

The `setuid ELF 32-bit LSB executable` tells us that this file is a program that we can run.

```bash
leviathan4@leviathan:~/.trash$ ./bin
01010100 01101001 01110100 01101000 00110100 01100011 01101111 01101011 01100101 01101001 00001010
```
Finding a tool to convert this for us is pretty difficult.
It's more efficient to use an online converter.
I dug around stackoverflow and found this solution:

```binary
leviathan4@leviathan:~/.trash$ ./bin | perl -lape '$_=pack"(B8)*",@F'
Tith4cokei
```

The password for the next level is `Tith4cokei`
