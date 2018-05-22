EMAIL VERIFICATION
==================

Provides API for E-Mail and Domain Verification. Options:   

+ Check email address against blacklist (editable textfile) If a domain service https://trashmail-blacklist.org/ updated weekly) Use the implementation on your own risk. **You maybe need a special license to call fiddlemail.com, mogelmail.de or any other domain related to this service.**
+ Check availability of mailhost. (MX and A Resource Record)
+ Validate Top Level Domain. (list of TLDs (punycode) pulled from IANA stored in local textfile, updated monthly)
+ Validate Domainname (Syntax)
+ Validate Hostname (Syntax)

Blacklisted domains are listed in an easy to edit text file **blacklist.txt** which is stored in the repository of this module.  

## API

```
// get module  
$mailcheck = $modules->get('EmailVerification');

// return bool/ string - automatted update of blacklist file
$mailcheck->blacklisted(email|domain)

// return bool - validate a top level domain, checks against IANA list
$mailcheck->validTLD(tld)

// return array of punycoded TLDs - cyclic updated, data pulled from IANA
$mailcheck->getTLDs(cycle=2592000)

// return bool - checks syntax converts to punycode
$mailcheck->validDomainName(domain);

// return bool - checks punycode encoded syntax 
$mailcheck->validHostName(host);  
  
// return bool - checks syntax and accessibility
$mailcheck->validHost(email|domain)

// add a single value to blacklist
$mailcheck->addToBlacklist(email|domain)
```

## License
[GNU-GPLv3](http://www.gnu.org/licenses/gpl-3.0.html)

## Author
kixe (Christoph Thelen)
