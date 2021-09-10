# docker-iis-php-e2e
## IIS PHP Container with MS SQL driver, node js and cypress e2e installed.

The repository contains docker images which PHP 7.4 x64, MS SQL Server drivers installed and optionally nodejs V14.
You can use one of the following tags
* `mbcom/docker-iis-php-e2e:php-iis-latest`
* `mbcom/docker-iis-php-e2e:node-latest` , which contains Node.JS in version 12
  
Make sure you fullfill the license requirements of the Software companies used here.

## Build
To build php-iis image, you must download the IIS Rewrite Module to `iis-php/rewrite_amd64_de-DE.msi` and you must download the Microsoft ODBC Driver 17 x64 for SQL Server to `iis-php/msodbcsql.msi`.
