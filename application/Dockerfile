FROM node:alpine

RUN mkdir -p /home/node/app && chown -R node:node /home/node/app

WORKDIR /home/node/app

COPY --chown=node:node package*.json ./

USER node

RUN npm cache clean --force --loglevel=error && npm install --verbose

COPY --chown=node:node . .

EXPOSE 3000

CMD [ "npm", "run", "dev" ]