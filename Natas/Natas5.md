# OverTheWire Project

### [Project Natas:](http://overthewire.org/wargames/natas/)

#### Natas Level 5

Alright, we're now on Level 5. There are about 30 more to go and I'm already feeling like this is difficult :(
But let's keep trying :)

Login and we're greeted with this message:
>Access disallowed. You are not logged in

The html code doesn't offer much help either:

```html
<div id="content">
Access disallowed. You are not logged in</div>
```

Alright, let's ask us ourselves: How does the website know we are not logged in?
Messing around led me to check the website's cookies.
We seek that there is a cookie called `loggedin` set to 0, but we want it set to 1.
To edit the cookie, open up developer tools on the browser and add a javascript command into the console:

```javascript
document.cookie="loggedin=1"
```

Refreshing the page submits the cookie and tells the website we are logged in.

**So we get the password for the next level which is
`aGoY4q2Dc6MgDq4oL4YtoKtyAg9PeHa1`.**
