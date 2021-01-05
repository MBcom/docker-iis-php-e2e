FROM mbcom/docker-iis-php-e2e:php-iis-latest

RUN powershell -command Invoke-WebRequest -Uri https://nodejs.org/dist/v14.15.4/node-v14.15.4-x64.msi -Outfile node.msi && node.msi /quiet && powershell -command rm node.msi -Force
