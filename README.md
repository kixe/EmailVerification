EMAIL VERIFICATION
==================

Checks an email address against blacklist and availability of mailhost. (MX and A Resource Record)

Blacklisted domains and email addresses are listed in an easy to edit text file **mogelmails.txt** which is stored in the repository of this module.

## Use

```

$mailcheck = $modules->get('EmailVerification');

$email = 'susi@spammer.example'; // your sanitized input
if($mailcheck->blacklisted($email)) echo 'Email Provider not allowed';
if(!$mailcheck->hostavailable($email)) echo 'Mailhost not available';


```

## Edit Exclusions List
Open (or create new) **mogelmails.txt** and edit your exclusions list.

Write one complete email address or one domainname per line.

```

badmail@example.org
spammer.example
virus.invalid

```

## License
[GNU-GPLv3](http://www.gnu.org/licenses/gpl-3.0.html)

## Author
kixe (Christoph Thelen)
