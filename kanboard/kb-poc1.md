# Exploit Title: Kanboard v1.2.44 - Cross-Site Scripting (XSS)
## Date: 24/4/2025
## Vendor Homepage: https://github.com/kanboard/kanboard
## Tested on: Debian Linux, Apache, Mysql
## Vendor: Kanboard
## Version: v1.2.44
## Exploit Description:
## Kanboard v1.2.44 suffers from Stored Cross-Site Scripting (XSS) Vulnerability in the 'name' parameter of the 'http://localhost/?controller=ProjectCreationController&action=create' form. This vulnerability allows attackers to inject malicious scripts into web pages viewed by other users. 
## Note: The default CSP blocks the javascript attack, tho it can be exploited if an instance is badly configured and at the moment it's vulnerable to CSS injection because of the unsafe-inline on the default CSP, so I think that would be also good to take a look into that and maybe remove that flag from the default CSP.
## ---------------------------------POC-----------------------------
1. User creates a project A
2. Attacker creates another project B and injects the payload in the 'name' parameter
```
payload: <meta http-equiv="refresh" content="2;url=http://example.com/" />
```
3. Victim views the project A and clicks 'Import Tasks' button
```
http://localhost/?controller=ProjectViewController&action=importTasks&project_id=1
```
4. The payload is executed

code sink:
https://github.com/kanboard/kanboard/blob/v1.2.44/app/Template/project_view/importTasks.php#L11


