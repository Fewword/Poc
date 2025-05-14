# Exploit Title: Opencart v4.1.0.3 - Cross-Site Scripting (XSS)
## Date: 14/5/2025
## Vendor Homepage: https://github.com/opencart/opencart
## Tested on: Debian Linux, Apache, Mysql
## Vendor: Opencart
## Version: v4.1.0.3
## Exploit Description:
## Opencart v4.1.0.3 suffers from Stored Cross-Site Scripting (XSS) Vulnerability in the 'Value' parameter of the customer/custom_field. This vulnerability allows attackers to inject malicious scripts into web pages viewed by other users.

## ---------------------------------POC-----------------------------
1. After logging in, navigate to the 'Customer' section and click on 'Custom Fields'
2. Click on the 'Add New' button
3. Choose 'Text' as the 'Type' and fill in the 'Value' field with the payload
    ```
    <script>alert('XSS')</script>
    ```
4. Click on the 'Save' button
5. Open the field created in step 3, and the payload is executed
