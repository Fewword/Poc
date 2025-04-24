# Exploit Title: LibreNMS v25.4.0 - Cross-Site Scripting (XSS)
## Date: 24/4/2025
## Vendor Homepage: https://github.com/librenms/librenms
## Tested on: Debian Linux, Apache, Mysql
## Vendor: LibreNMS
## Version: v25.4.0
## Exploit Description:
## LibreNMS v25.4.0 suffers from Stored Cross-Site Scripting (XSS) Vulnerability in the 'group name' parameter of the 'http://localhost/poller/groups' form. This vulnerability allows attackers to inject malicious scripts into web pages viewed by other users.

## ---------------------------------POC-----------------------------
Before Setting: Enable 'distributed_poller' in http://localhost/settings/poller/distributed
1. Attacker creates a new poller group and injects the payload in the 'group name' parameter
```
payload: <script>alert('XSS')</script>
```
2. Victim navigates to the 'http://localhost/addhost' to add a new host
3. The payload is executed

code sink:
https://github.com/librenms/librenms/blob/25.4.0/includes/html/pages/addhost.inc.php#L284