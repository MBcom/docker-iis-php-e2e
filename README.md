# docker-iis-php-e2e
## IIS PHP Container with MS SQL driver, and optionally Node.JS

The repository contains Windows Docker images which you can use to host a PHP Web app using IIS in a Docker container.
The image also contains MS SQL drivers needed to connect to a MS SQL Database and Composer to let you install your requirements.
Composer also nakes it easy to install PHPUnit therefore it is easy to use this container for your Unit Tests.
This repository also offers images having Node.JS installed therefore you can use this image in your CI/CD Pipelines to build your frontend apps too.
You can find available configurations in the table below.  
  
Feel free to contribute any additional combination.

## Available tags
|Tag|PHP Version|MS SQL Driver Version|Composer Version|Node JS Version|
|---|-----------|---------------------|----------------|---------------|
|[php-iis-latest](https://hub.docker.com/layers/mbcom/docker-iis-php-e2e/php-iis-latest/images/sha256-13413ab454679957c962f6174988023c31f34bc463f0055417a95ef64cd2c68b?context=explore)|[7.4.33 NTS x64](https://windows.php.net/downloads/releases/php-7.4.33-nts-Win32-vc15-x64.zip)|[5.8.1](https://windows.php.net/downloads/pecl/releases/sqlsrv/5.8.1/php_sqlsrv-5.8.1-7.4-nts-vc15-x64.zip)|[2.1.6](https://getcomposer.org/download/2.1.6/composer.phar)|x|
|[node-latest](https://hub.docker.com/layers/mbcom/docker-iis-php-e2e/node-latest/images/sha256-b9b0b6a5bd130a45b4f9a4bf643bb634c73f921323a9b34757ab335b1248462e?context=explore)|[7.4.33 NTS x64](https://windows.php.net/downloads/releases/php-7.4.33-nts-Win32-vc15-x64.zip)|[5.8.1](https://windows.php.net/downloads/pecl/releases/sqlsrv/5.8.1/php_sqlsrv-5.8.1-7.4-nts-vc15-x64.zip)|[2.1.6](https://getcomposer.org/download/2.1.6/composer.phar)|[16.18.1](https://nodejs.org/dist/v16.18.1/node-v16.18.1-x64.msi)|
|[php-iis-7.4.33_mssql5.8.1](https://hub.docker.com/layers/mbcom/docker-iis-php-e2e/php-iis-7.4.33_mssql5.8.1/images/sha256-13413ab454679957c962f6174988023c31f34bc463f0055417a95ef64cd2c68b?context=explore1)|[7.4.33 NTS x64](https://windows.php.net/downloads/releases/php-7.4.33-nts-Win32-vc15-x64.zip)|[5.8.1](https://windows.php.net/downloads/pecl/releases/sqlsrv/5.8.1/php_sqlsrv-5.8.1-7.4-nts-vc15-x64.zip)|[2.1.6](https://getcomposer.org/download/2.1.6/composer.phar)|x|
|[node-v16.18.1](https://hub.docker.com/layers/mbcom/docker-iis-php-e2e/node-v16.18.1/images/sha256-b9b0b6a5bd130a45b4f9a4bf643bb634c73f921323a9b34757ab335b1248462e?context=explore)|[7.4.33 NTS x64](https://windows.php.net/downloads/releases/php-7.4.33-nts-Win32-vc15-x64.zip)|[5.8.1](https://windows.php.net/downloads/pecl/releases/sqlsrv/5.8.1/php_sqlsrv-5.8.1-7.4-nts-vc15-x64.zip)|[2.1.6](https://getcomposer.org/download/2.1.6/composer.phar)|[16.18.1](https://nodejs.org/dist/v16.18.1/node-v16.18.1-x64.msi)|
Make sure you fullfill the license requirements of the Software companies used here.

## Build
To build php-iis image, you must download the IIS Rewrite Module to `iis-php/rewrite_amd64_de-DE.msi` and you must download the Microsoft ODBC Driver 17 x64 for SQL Server to `iis-php/msodbcsql.msi`.
