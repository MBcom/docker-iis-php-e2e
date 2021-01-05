FROM mcr.microsoft.com/windows/servercore:ltsc2019 as base

RUN powershell -command Add-WindowsFeature Web-Server

ADD https://windows.php.net/downloads/releases/php-7.2.34-nts-Win32-VC15-x86.zip php.zip
RUN powershell -command Expand-Archive -Path php.zip -DestinationPath C:\php && powershell -command Remove-Item php.zip -Force
ADD https://windows.php.net/downloads/pecl/releases/sqlsrv/5.8.0/php_sqlsrv-5.8.0-7.2-nts-vc15-x86.zip sql.zip 
RUN powershell -command Expand-Archive -Path sql.zip -DestinationPath C:\php\ext && powershell -command Remove-Item sql.zip -Force
ADD https://aka.ms/vs/16/release/vc_redist.x86.exe vc_redist.exe
RUN vc_redist.exe /install /quiet && powershell -command Remove-Item vc_redist.exe -Force
ADD https://curl.haxx.se/ca/cacert.pem ca.pem
RUN powershell -command cp ca.pem "C:\php\\" && powershell -command cp c:\php\php.ini-production c:\php\php.ini
RUN powershell -command echo '[PHP_FILEINFO]' 'extension=php_fileinfo.dll' ' ' '[PHP_SQLSRV_72_NTS_X86]' 'extension=php_sqlsrv.dll' ' ' 'curl.cainfo = c:\php\ca.pem' >> C:\php\php.ini

RUN dism.exe /Online /Enable-Feature /FeatureName:IIS-CGI /All 
RUN     %windir%\system32\inetsrv\appcmd.exe set config /section:system.webServer/fastCgi /+[fullPath='c:\PHP\php-cgi.exe']
RUN     %windir%\system32\inetsrv\appcmd.exe set config /section:system.webServer/handlers /+[name='PHP_via_FastCGI',path='*.php',verb='*',modules='FastCgiModule',scriptProcessor='c:\PHP\php-cgi.exe',resourceType='Either'] 
RUN     %windir%\system32\inetsrv\appcmd.exe set config -section:system.webServer/fastCgi /[fullPath='c:\PHP\php-cgi.exe'].instanceMaxRequests:10000 
RUN     %windir%\system32\inetsrv\appcmd.exe set config -section:system.webServer/fastCgi /+[fullPath='c:\PHP\php-cgi.exe'].environmentVariables.[name='PHP_FCGI_MAX_REQUESTS',value='10000'] 
RUN     %windir%\system32\inetsrv\appcmd.exe set config -section:system.webServer/fastCgi /+[fullPath='c:\PHP\php-cgi.exe'].environmentVariables.[name='PHPRC',value='C:\PHP'] 
RUN     %windir%\system32\inetsrv\appcmd.exe set config /section:defaultDocument /enabled:true /+files.[value='index.php'] 
RUN     setx PATH /M %PATH%;C:\PHP 
RUN     setx PHP /M "C:\PHP"
    
RUN mkdir c:\web
WORKDIR c:\\web

CMD  ["C:\\ServiceMonitor.exe", "w3svc"]
