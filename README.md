EMAIL VERIFICATION
==================

Provides API for E-Mail and Domain Verification. Options:   

+ Check email address against blacklist (editable textfile pulled from service fiddlemail.com/mogelmail.de updated weekly) Use the implementation on your own risk. **You maybe need a special license to call fiddlemail.com, mogelmail.de or any other domain related to this service.**
+ Check availability of mailhost. (MX and A Resource Record)
+ Validate Top Level Domain. (list of TLDs (punycode) pulled from IANA stored in local textfile, updated monthly)
+ Validate Domainname (Syntax)
+ Validate Hostname (Syntax)

Blacklisted domains are listed in an easy to edit text file **blacklist.txt** which is stored in the repository of this module.  

## API

```
$mailcheck = $modules->get('EmailVerification');

$mailcheck->blacklisted(email|domain) // return bool/ string
$mailcheck->validTLD(tld) // validate a top level domain return bool
$mailcheck->getTLDs(cycle=2592000) // get Array of punycoded TLDs, cyclic updated data pulled from IANA
$mailcheck->validDomainName(domain); // return bool
$mailcheck->validHostName(host); // return bool/ string
$mailcheck->validHost(email|domain) // return bool
$mailcheck->addToBlacklist(email|domain) // add single value
```

## License
[GNU-GPLv3](http://www.gnu.org/licenses/gpl-3.0.html)

## Author
kixe (Christoph Thelen)
