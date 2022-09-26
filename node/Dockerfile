FROM mbcom/docker-iis-php-e2e:php-iis-latest

RUN powershell -command Invoke-WebRequest -Uri https://nodejs.org/dist/v16.9.1/node-v16.9.1-x64.msi -Outfile node.msi && node.msi /quiet && powershell -command rm node.msi -Force
