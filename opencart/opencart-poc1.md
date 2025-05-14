# Exploit Title: Opencart v4.1.0.3 - Cross-Site Scripting (XSS)
## Date: 14/5/2025
## Vendor Homepage: https://github.com/opencart/opencart
## Tested on: Debian Linux, Apache, Mysql
## Vendor: Opencart
## Version: v4.1.0.3
## Exploit Description:
## Opencart v4.1.0.3 suffers from Stored Cross-Site Scripting (XSS) Vulnerability in the 'code' parameter of the catalog/identifier.form. This vulnerability allows attackers to inject malicious scripts into web pages viewed by other users.

## ---------------------------------POC-----------------------------
1. After logging in, navigate to the 'Catalog' section and click on 'Identifiers'
2. Click on the 'Add New' button
3. Fill in the 'Code' field with the payload
    ```
    <script>alert('XSS')</script>
    ```
4. Click on the 'Save' button
5. Navigate to the 'Catalog' section and click on 'Products'
6. Click on the 'Add New' button
7. Navigate to the 'Data' tab and select the identifier created in step 3 from the 'Product Codes' dropdown
8. Click on the 'Save' button
9. The payload is executed.
