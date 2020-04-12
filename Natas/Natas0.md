# OverTheWire Project

### [Project Natas:](http://overthewire.org/wargames/natas/)

#### Leviathan Level 0

Welcome to Project Natas, this wargame is quite long with 34 levels in total.
Unlike Project Bandit and Project Leviathan, Natas is based on serverside web-security without an SSH login.
Instead, each level has its own website as stated in the README.

We know that the password for each level is stored in `/etc/natas_webpass/` although we most likely will not have immediate access.

Level0 info:
>Username: natas0
Password: natas0
URL:      http://natas0.natas.labs.overthewire.org

So go to the website and use the login credentials.

 You can view the html code of the website by going to `view-source:http://natas0.natas.labs.overthewire.org/`

 Chrome shows us a hidden comment on the website.

```html
 <div id="content">
You can find the password for the next level on this page.

<!--The password for natas1 is gtVrDuiDfck831PqWsLEZy5gyDz1clto -->
</div>
```
So we get the password for the next level which is
`gtVrDuiDfck831PqWsLEZy5gyDz1clto`.
