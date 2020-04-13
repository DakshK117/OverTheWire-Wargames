# OverTheWire Project

### [Project Natas:](http://overthewire.org/wargames/natas/)

#### Natas Level 6

On level 6, we have a submit form and can view the source code for the form by clicking the `View sourecode`.

```php
<?

include "includes/secret.inc";

    if(array_key_exists("submit", $_POST)) {
        if($secret == $_POST['secret']) {
        print "Access granted. The password for natas7 is <censored>";
    } else {
        print "Wrong secret";
    }
    }
?>
```

It seems that the php form checks if the `$_POST` input is equal to the variable `$secret`.
Unfortunately, we don't know the value of the variable. However, the code does tell us that it includes the file `secret.inc`
In natas2, we visited a subdirectory to view the password file. We can try visiting the secret.inc file here too.
Going to "http://natas6.natas.labs.overthewire.org/includes/secret.inc" gives us the variable `$secret = "FOEIUWGHFEEUHOFUOIU";`.

Enter it into the php form to get the password for Natas7.

**So we get the password for the next level which is
`7z3hEENjQtflzgnT29q7wAvMNfZdh0i9`.**
