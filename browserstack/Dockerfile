FROM mbcom/docker-iis-php-e2e:node-latest

COPY firefox.msi .
COPY chrome.msi .
#COPY edge.msi .

RUN firefox.msi 
RUN chrome.msi
#RUN msiexec /i edge.msi /qn /norestart

SHELL ["powershell"]

#RUN rm firefox.msi -Force && rm chrome.msi -Force #&& rm edge.msi -Force
RUN rm chrome.msi -Force 
RUN rm firefox.msi -Force 
