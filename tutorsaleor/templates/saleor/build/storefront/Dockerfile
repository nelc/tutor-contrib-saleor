FROM node:18-alpine

RUN apk add --no-cache git

WORKDIR /app

RUN git clone -b {{ SALEOR_STOREFRONT_BRANCH }} {{ SALEOR_STOREFRONT_REPOSITORY }} storefront

WORKDIR /app/storefront

RUN npm install

EXPOSE 3000
