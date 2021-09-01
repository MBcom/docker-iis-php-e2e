# docker-iis-php-e2e
## IIS PHP Container with MS SQL driver, node js and cypress e2e installed.

The repository contains docker images which PHP, MS SQL Server drivers installed and optionally nodejs V12, Chrome Browser V87 and Firefox V84, and cypress V6.2.  
You can use one of the following tags
* `mbcom/docker-iis-php-e2e:php-iis-latest`
* `mbcom/docker-iis-php-e2e:node-latest` , which contains Node.JS in version 12
* `mbcom/docker-iis-php-e2e:browserstack-latest` , which contains Node.JS in version 12, Google Chrome in version 87 and Mozilla Firefox in version 84
* `mbcom/docker-iis-php-e2e:cypress-latest` ,  which contains Node.JS in version 12, Google Chrome in version 87 , Mozilla Firefox in version 84 and Cypress in Version 6.2  
  
Make sure you fullfill the license requirements of the Software companies used here.

## Build
To build php-iis image, you must download the IIS Rewrite Module to `iis-php/rewrite_amd64_de-DE.msi` and you must download the Microsoft ODBC Driver 17 x64 for SQL Server to `iis-php/msodbcsql.msi`.