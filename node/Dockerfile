FROM mbcom/docker-iis-php-e2e:php-iis-latest

ADD https://nodejs.org/dist/v16.18.1/node-v16.18.1-x64.msi  node.msi
RUN node.msi /quiet && powershell -command rm node.msi -Force
