# OverTheWire Project

### [Project Leviathan:](http://overthewire.org/wargames/leviathan/)

#### Leviathan Level 2 -> 3
> There is no information for this level, intentionally.

SSH into the second level using the password `Ahdiemoo1j`

By learning from previous levels, we know that the password for this level is stored at `/etc/leviathan_pass/leviathan4`, but we don't have access to that file.

Like the previous level, there is a executable named `level3` which requires a password.
Run `ltrace` to check how the executable file runs.

```bash
leviathan3@leviathan:~$ ltrace ./level3
__libc_start_main(0x565557b4, 1, 0xffffd754, 0x56555870 <unfinished ...>
strcmp("h0no33", "kakaka")                                                = -1
printf("Enter the password> ")                                            = 20
fgets(Enter the password> password
"password\n", 256, 0xf7fc55a0)                                      = 0xffffd560
strcmp("password\n", "snlprintf\n")                                       = -1
puts("bzzzzzzzzap. WRONG"bzzzzzzzzap. WRONG
)                                                = 19
+++ exited (status 0) +++
```
Since we don't know the password, type something random and you can see the program checks if the input is the same as the required password which is `snlprintf`

If we use the correct password, the program gives us permission to
view the next level's pass at `/etc/leviathan_pass/leviathan3`

```bash
leviathan3@leviathan:~$ ./level3
Enter the password> snlprintf
[You've got shell]!
$ cat /etc/leviathan_pass/leviathan4
vuH0coox6m
```

The password for leviathan4 is `vuH0coox6m`
