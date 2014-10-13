EMAIL VERIFICATION
===================

Checks an email address against blacklist and availability of mailhost. (MX and A Resource Record)

Blacklisted domains and email addresses are listed in an easy to edit text file *mogelmails.txt* which is stored in the repository of this module.

## Installation
as usual

## Use

```

$mailcheck = $modules->get('EmailCheck');

$email = 'susi@trashmail.com'; // your sanitized input
if($mailcheck->blacklisted($email)) echo 'Email Provider not allowed';
if(!$mailcheck->hostavailable($email)) echo 'Mailhost not available';


```

## Edit Exclusions List
open (or create new) mogelmails.txt and edit your exclusions list
write one complete email address or one domainname per line

```

badmail@example.org
spammer.example
virus.invalid

```

## License
[GNU_GPLv3](http://www.gnu.org/licenses/gpl-3.0.html)

## Author
kixe (Christoph Thelen)
