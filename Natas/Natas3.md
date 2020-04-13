# OverTheWire Project

### [Project Natas:](http://overthewire.org/wargames/natas/)

#### Natas Level 3

Level 3 only tells us "There is nothing on this page"
Looking at the html source code lets us see a comment:

```html
<div id="content">
There is nothing on this page
<!-- No more information leaks!! Not even Google will find it this time... -->
</div>
```

One way people find directories and files are through scrapers that browse the internet for all files that are not hidden.

Going to 'http://natas2.natas.labs.overthewire.org/robots.txt' shows us another interesting comment:

'''
User-agent: *
Disallow: /s3cr3t/
'''

So apparently scrapers are not allowed to access a subdirectory: '/s3cr3t/'

Going to 'http://natas3.natas.labs.overthewire.org/s3cr3t/' shows the users.txt file which has the password for natas4

So we get the password for the next level which is
`Z9tkRkWmpt9Qr7XrR5jWRkgOU901swEZ`.
