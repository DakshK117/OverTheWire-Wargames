# OverTheWire Project

### [Project Natas:](http://overthewire.org/wargames/natas/)

#### Leviathan Level 2

We login into level 2 and are greeted with very little information. The website says that there's nothing available on the site, so we should take a look at the html code for the site.

looking at the page source shows an image file being uploaded.

```html
<div id="content">
There is nothing on this page
<img src="files/pixel.png">
</div>
```

We can check if the files directory is accessible from the website. Going to 'http://natas2.natas.labs.overthewire.org/files/'
There's a users.txt file which has a list of usernames and passwords, including natas3

So we get the password for the next level which is
`sJIJNW6ucpu6HPZ1ZAchaDtwd7oGrD14`.
