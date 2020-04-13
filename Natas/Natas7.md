# OverTheWire Project

### [Project Natas:](http://overthewire.org/wargames/natas/)

#### Natas Level 7

We're now on level 7, login using the credentials from level 6.

There are two links, `Home` and `About`.
The html code gives us a hint:

```html
<div id="content">

<a href="index.php?page=home">Home</a>
<a href="index.php?page=about">About</a>
<br>
<br>

<!-- hint: password for webuser natas8 is in /etc/natas_webpass/natas8 -->
</div>
```
Since the password is located at the path `/etc/natas_webpass/natas8`, we can also see how the website accesses the pages for Home and About. Try using `index.php?page=/etc/natas_webpass/natas8` and we go to a page with the password.


**So we get the password for the next level which is
`DBfUBfqQG69KvJvJ1iAbMoIpwSNQ9bWe`.**
