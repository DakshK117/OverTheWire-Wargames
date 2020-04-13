# OverTheWire Project

### [Project Natas:](http://overthewire.org/wargames/natas/)

#### Natas Level 8

Login to Level 8 and we see a familiar submission form.

```php
<?

$encodedSecret = "3d3d516343746d4d6d6c315669563362";

function encodeSecret($secret) {
    return bin2hex(strrev(base64_encode($secret)));
}

if(array_key_exists("submit", $_POST)) {
    if(encodeSecret($_POST['secret']) == $encodedSecret) {
    print "Access granted. The password for natas9 is <censored>";
    } else {
    print "Wrong secret";
    }
}
?>
```

So the code checks if the input is equal to the encoded string `3d3d516343746d4d6d6c315669563362`. However, we have to decode that string first. I ran a php script that reversed the encodeSecret function.

```php
<?
echo base64_decode(strrev(hex2bin("3d3d516343746d4d6d6c315669563362")));
?>
```

The result is `oubWYf2kBq`. After submitting it into the form, we get the password.


**So we get the password for the next level which is
`W0mMhUcRRnG8dcghE4qvk3JA9lGt8nDl`.**
