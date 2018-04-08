# OverTheWire Project

### [Project Leviathan:](http://overthewire.org/wargames/leviathan/)

#### Leviathan Level 0
> There is no information for this level, intentionally.

The game has given no information on how to solve the level but we know the login information and host.
SSH into the host and enter the password which is `leviathan0`

```
ssh leviathan0@leviathan.labs.overthewire.org -p 2223
```

Out of habit from the Bandit waragme, go ahead and run `ls -l -a` to look for any hidden files or folders.
There's a interesting backup directory which has a file called `bookmarks.html`
`cat bookmarks.html` provides a rather large amount of data. We're looking specifically for passwords, so go ahead and `grep` the file for "pass".
You should get this output:
```
leviathan0@leviathan:~/.backup$ cat bookmarks.html | grep pass
<DT><A HREF="http://leviathan.labs.overthewire.org/passwordus.html | This will be fixed later, the password for leviathan1 is rioGegei8m" ADD_DATE="1155384634" LAST_CHARSET="ISO-8859-1" ID="rdf:#$2wIU71">password to leviathan1</A>
```

**_Yay_**, the password for the next level is `rioGegei8m`
