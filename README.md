EMAIL VERIFICATION
==================

Functional **API** for E-Mail and Domain Verification.

+ **Email address verification** against domain black- and whitelist (automated updates via online service [trashmail-blacklist.org](https://trashmail-blacklist.org))
+ Determination of **availability of a mailhost**. (MX and A Resource Record)
+ Validation of **Top Level Domains.** (list of TLDs (punycode encoded) pulled from IANA stored in local textfile, automated monthly update)
+ **Syntax validation** of **domainnames**
+ **Syntax validation** of **hostnames** (punycode encoded)

Domains are listed in easy to edit text files **blacklist.txt** and **whitelist.txt** which are stored in the repository of this module.  

## API Usage

```
// get module  
$mailcheck = $modules->get('EmailVerification');

// return bool/ string - automatted update of blacklist file
$mailcheck->blacklisted(email|domain)

// return bool - validate a top level domain, checks against IANA list
$mailcheck->validTLD(tld)

// return array of punycoded TLDs - cyclic updated, data pulled from IANA
$mailcheck->getTLDs(cycle=2592000)

// return string - domain part of an email address
$mailcheck->getDomain($str)

// return bool - checks syntax converts to punycode
$mailcheck->validDomainName(domain);

// return bool - checks punycode encoded syntax 
$mailcheck->validHostName(host);  
  
// return bool - checks syntax and accessibility
$mailcheck->validHost(email|domain)

// add a single value to blacklist, remove from whitelist
// return false or string (domain)
$mailcheck->blacklist(email|domain)

// add a single value to whitelist, remove from blacklist
// return false or string (domain)
$mailcheck->whitelist(email|domain)
```

## License
[GNU-GPLv3](http://www.gnu.org/licenses/gpl-3.0.html)

## Author
kixe (Christoph Thelen)
