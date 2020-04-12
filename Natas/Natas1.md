# OverTheWire Project

### [Project Natas:](http://overthewire.org/wargames/natas/)

#### Leviathan Level 1

Alright, we can login to the site with the credentials found from the previous level.
However, right clicking is blocked but the password is still on the page.
We can view the page source by going to: `view-source:http://natas1.natas.labs.overthewire.org/`

 Chrome shows us a hidden comment on the website.

```html
<div id="content">
You can find the password for the
next level on this page, but rightclicking has been blocked!

<!--The password for natas2 is ZluruAthQk7Q2MqmDeTiUij2ZvWy2mBi -->
</div>
```
So we get the password for the next level which is
`ZluruAthQk7Q2MqmDeTiUij2ZvWy2mBi`.
