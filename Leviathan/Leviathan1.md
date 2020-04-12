# OverTheWire Project

### [Project Leviathan:](http://overthewire.org/wargames/leviathan/)

#### Leviathan Level 0 -> 1
> There is no information for this level, intentionally.

Start by logging in to level 1 with the password acquired from level 0, which was `rioGegei8m`
```bash
ssh leviathan1@leviathan.labs.overthewire.org -p 2223
```
There is a file called `check` which seems to be a executable. Running the program asks for a password and stops if you enter the wrong password.

We can run `ltrace ./check` to follow the program as it runs. After entering a wrong passwd, the program checks if the input was correct.

```bash
leviathan1@leviathan:~$ ltrace ./check
__libc_start_main(0x804858d, 1, 0xffffd6f4, 0x8048670 <unfinished ...>
printf("password: ")                                                                                              = 10
getchar(0x80486f0, 0, 0xf7e45830, 0x80486bbpassword: incorrectpasswd
)                                                                      = 105
getchar(0x80486f0, 0, 0xf7e45830, 0x80486bb)                                                                      = 110
getchar(0x80486f0, 0, 0xf7e45830, 0x80486bb)                                                                      = 99
strcmp("inc", "sex")                                                                                              = -1
puts("Wrong password, Good Bye ..."Wrong password, Good Bye ...
)                                                                              = 29
+++ exited (status 0) +++
```
So apparently the password is "sex". Run the check program and it provides you a shell.
Fortunately, this gives you access to the `leviathan2` file in the `/etc/leviathan_pass` directory.
`cat /etc/leviathan_pass/leviathan2` to get the password

**The password for leviathan2 is `ougahZi8Ta`**
