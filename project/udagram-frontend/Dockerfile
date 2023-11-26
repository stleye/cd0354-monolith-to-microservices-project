
FROM beevelop/ionic:latest AS ionic

WORKDIR /usr/src/app

COPY package*.json ./
RUN npm install --force

COPY . .

ARG NODE_OPTIONS=--openssl-legacy-provider

RUN ionic build

FROM nginx:alpine

COPY --from=ionic  /usr/src/app/www /usr/share/nginx/html
