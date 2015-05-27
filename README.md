EMAIL VERIFICATION
==================

Provides API for E-Mail and Domain Verification. Options:   

+ Check email address against blacklist (editable textfile pulled from service mogelmail.de updated weekly)
+ Check availability of mailhost. (MX and A Resource Record)
+ Validate Top Level Domain. (list of TLDs (punycode) pulled from IANA stored in local textfile, updated monthly)
+ Validate Domainname (Syntax)
+ Validate Hostname (Syntax)

Blacklisted domains are listed in an easy to edit text file **mogelmails.txt** which is stored in the repository of this module.  

## API

```

$mailcheck = $modules->get('EmailVerification');

$mailcheck->getTLDs(cycle=2592000) // get Array of punycoded TLDs, cyclic updated
$mailcheck->validDomainName(domain); // return bool
$mailcheck->validHostName(host); // return bool/ string
$mailcheck->blacklisted(email|domain) // return bool/ string
$mailcheck->hostavailable(email|domain) // return bool

$mailcheck->addToBlacklist(email|domain) // add single value
$mailcheck->add(string,replace=false) // create, overwrite, update blacklist, single or multiple value
$mailcheck->clean() // cleanup blacklist file (remove empty strings & duplicates, sort)

```

## License
[GNU-GPLv3](http://www.gnu.org/licenses/gpl-3.0.html)

## Author
kixe (Christoph Thelen)
