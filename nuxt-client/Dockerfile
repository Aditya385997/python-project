FROM node:12.20.0

ENV APP_DIR /app/

WORKDIR /app

COPY .env /app/.env

ADD . .

RUN yarn install

RUN yarn build

EXPOSE 3001


