# OverTheWire Project

### [Project Natas:](http://overthewire.org/wargames/natas/)

#### Natas Level 4

Login to Level 4 and we see "Access disallowed"

```html
<div id="content">
Access disallowed. You are visiting from "" while authorized users should come only from "http://natas5.natas.labs.overthewire.org/"
<br/>
<div id="viewsource"><a href="index.php">Refresh page</a></div>
</div>
```

So the issue here is that the website checks the referrer and knows which website we visit from. However, we can't access Natas5 and visit Natas4 from there. We need to spoof the referrer and make it seem like we are visiting from Natas5. There are several chrome extensions or scripts that can do this. I used `referrer control` extension for chrome.

**So we get the password for the next level which is
`iX6IOfmpN7AYOQGPwtn3fXpbaJVJcHfq`.**
