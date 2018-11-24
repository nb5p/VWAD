FROM alpine

RUN apk add --no-cache npm && \
        rm -rf /var/cache/apk/*
ENV NPM_CONFIG_PREFIX=/.npm-global
RUN npm install -g --unsafe-perm express-generator

WORKDIR /np-xss
RUN /.npm-global/bin/express -e .
RUN npm install

COPY np/index.ejs ./views/index.ejs
COPY np/index.js ./routes/index.js

EXPOSE 3000
CMD npm start
