FROM mcr.microsoft.com/vscode/devcontainers/javascript-node:0.203.3-14

EXPOSE 4321 35729

ENV NPM_CONFIG_PREFIX=/usr/app/.npm-global \
  PATH=$PATH:/usr/app/.npm-global/bin

VOLUME /usr/app/spfx
WORKDIR /usr/app/spfx
RUN useradd --create-home --shell /bin/bash spfx && \
    usermod -aG sudo spfx && \
    chown -R spfx:spfx /usr/app

USER spfx

RUN npm i -g gulp@4 yo @microsoft/generator-sharepoint@1.13.1

CMD /bin/bash