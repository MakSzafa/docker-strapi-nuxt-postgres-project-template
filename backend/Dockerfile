FROM node:18-alpine

RUN apk update && apk add --no-cache build-base gcc autoconf automake zlib-dev libpng-dev nasm bash vips-dev

WORKDIR /opt/
COPY package.json ./
RUN npm install

WORKDIR /opt/app
COPY . .

ENV PATH /opt/node_modules/.bin:$PATH

RUN chown -R node:node /opt/app
USER node

RUN ["npm", "run", "build"]
EXPOSE 1337
CMD ["npm", "run", "develop"]
