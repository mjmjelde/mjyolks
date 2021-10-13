FROM node:16

LABEL author="Matthew Mjelde" maintainer="webmaster@mjmfighter.com"

RUN npm install -g typescript@4.3.5

USER container
ENV USER=container  HOME=/home/container
WORKDIR /home/container

COPY        ./entrypoint.sh /entrypoint.sh
CMD         [ "/bin/bash", "/entrypoint.sh" ]
