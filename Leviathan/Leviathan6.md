# OverTheWire Project

### [Project Leviathan:](http://overthewire.org/wargames/leviathan/)

#### Leviathan Level 3 -> 4
> There is no information for this level, intentionally.

This the second to last level for Project Leviathan
The password for the previous level was `UgaoFee4li`

This level takes some creativity.
The directory has only one executable `leviathan6`

```bash
leviathan6@leviathan:~$ ls -l
total 8
-r-sr-x--- 1 leviathan7 leviathan6 7452 Oct 29 21:17 leviathan6
leviathan6@leviathan:~$ ./leviathan6
usage: ./leviathan6 <4 digit code>
```
The file is an executable which requires a 4-digit pin which we do not know.
If you enter the wrong pin, the program returns `Wrong`
The simplest idea would be to run a shell script to brute-force this executable by entering every combination from 0000 to 9999

```bash
leviathan6@leviathan:~$ for i in {0000..9999}; do echo $i; res=`./leviathan6 $i`; echo $res; [ $res != "Wrong" ] && break; done
```

This line of code uses a for-loop to enter every number from 0000 till 9999 to find the password for the executable.

`[ $res != "Wrong" ] && break;` checks if the executable *does not* return `Wrong` and stops the loop.

After a minute or two, the loop stops at the number `7123`.

```bash
leviathan6@leviathan:~$ ./leviathan6 7123
$ cat /etc/leviathan_pass/leviathan7
ahy7MaeBo9
```

Running `./leviathan6` with the correct pin gives you a shell with leviathan7 permissions.
Using `cat /etc/leviathan_pass/leviathan7` returns `ahy7MaeBo9`

The password found for the last level is `ahy7MaeBo9`. 
