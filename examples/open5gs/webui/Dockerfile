FROM node:13-buster

RUN apt update && apt install -y git && \
    git clone https://github.com/open5gs/open5gs.git && \
    apt-get clean autoclean && \
    apt-get autoremove --yes && \
    rm -rf /var/lib/{apt,dpkg,cache,log}/

WORKDIR /open5gs/webui

RUN npm install && \
    npm run build
