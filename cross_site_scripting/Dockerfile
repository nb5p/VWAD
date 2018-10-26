FROM alpine

RUN apk add --no-cache npm && \
        rm -rf /var/cache/apk/*
ENV NPM_CONFIG_PREFIX=/.npm-global
RUN npm install -g --unsafe-perm express-generator

WORKDIR /xss
RUN /.npm-global/bin/express -e .
RUN npm install

COPY index.ejs ./views/index.ejs
COPY index.js ./routes/index.js

EXPOSE 3000
CMD npm start
